<script>
	import * as THREE from 'three';
	import * as SC from 'svelte-cubed';
  import {onMount} from 'svelte';

	let width = 1;
	let height = 1;
	let depth = 1;

	let spinX = 1;
  let spinY = 0;

  let x = 0;
  let y = 1;

  let j;
  let i = 0;
  let m = 0;

  SC.onFrame(() => {
    spinX = Math.cos(x) + y;
    spinY = Math.sin(x) - y * 1.1;
    x += 0.01;
    y += 0.01;

    i += 0.01;
    j = 0.2 * Math.sin(1.5* x) + 0.2;

    m = 0.6 * Math.sin(3* x) + 0.2;

  });

  onMount( () => {

  });
	

</script>

<SC.Canvas
	antialias
	background={new THREE.Color('#3BB9FF')}
	fog={new THREE.FogExp2('#3BB9FF', 0.1)}
	shadows
>

	<SC.Group position={[0, -height / 2, 0]}>
		<SC.Mesh
			geometry={new THREE.PlaneGeometry(50, 50)}
			material={new THREE.MeshStandardMaterial({ color: 'black' })}
			rotation={[-Math.PI / 2, 0, 0]}
			receiveShadow
		/>

    <SC.Primitive
			object={new THREE.GridHelper(50, 50, 'green', 'green')}
			position={[0, 0, 0]}
		/>
		
	</SC.Group>

  <!-- 

    ************
    Sixth Layer 
    ************
  
  -->

  <!-- Orange -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.60, 0]}
    
  />

  <!-- Purple -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: m
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.60 + j, 0]}
    rotation={[0, spinX, 0]}
  />

  <!-- Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.60, 0.12]}
  />

  <!-- Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.60, -0.12]}
  />

  <!-- Mint -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.60, 0]}
  />

  <!-- 

    ************
    Fifth Layer 
    ************
  
  -->


  <!-- Dark Grey -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.48, -0.24]}
  />

  <!-- Aqua -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.48, -0.12]}
    rotation={[0, spinX, 0]}
  />

  <!-- Grey -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.48, -0.12]}
  />

  <!-- Black -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.48, -0.24]}
  />

  <!-- Red -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.48, -0.12]}
  />

  <!-- Lime -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.48, 0.12]}
  />

  <!-- Copper -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.48, -0.12]}
  />

  <!-- Strawberry -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.48, 0]}
  />

  <!-- Baby Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.48, 0.12]}
  />

  <!-- Cool White -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: m
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.48, 0.24 + j * 0.8]}
  />

  <!-- Gross Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.48, 0.24]}
  />

  <!-- Weird Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.48, 0.24]}
  />

  <!-- Royal Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.48, 0.12]}
  />

  <!-- Rose -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.48, 0.12]}
  />

  <!-- Orange -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.48, 0]}
  />

  <!-- Purple -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.48, 0]}
  />

  <!-- Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.48, 0.12]}
  />

  <!-- Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.48, -0.12]}
  />

  <!-- Limestone -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.48, -0.24]}
  />

  <!-- Green -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.48, 0]}
  />

  <!-- Mint -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.48, 0]}
  />

  <!-- 

    ************
    Forth Layer 
    ************
  
  -->

  <!-- Bright Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.36, 0.36, -0.12]}
  />
  

  <!-- Bright Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.36, 0.36, 0]}
  />

  <!-- Bright Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: m
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.36 - j * 0.5, 0.36, 0.12]}
    rotation={[spinY, 0, 0]}
  />

  <!-- Bright Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.36, -0.24]}
  />

  <!-- Dark Grey -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.36, -0.24]}
  />

  <!-- Aqua -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.36, -0.12]}
  />

  <!-- Grey -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.36, -0.12]}
  />

  <!-- Black -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.36, -0.24]}
    rotation={[0, spinX, 0]}
  />

  <!-- Red -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.36, -0.12]}
  />

  <!-- Lime -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.36, 0.12]}
  />

  <!-- Lavender -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.36, 0.36, 0.12]}
  />

  <!-- Lavender -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: m
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.36 + j * 0.8, 0.36, 0]}
  />

  <!-- Lavender -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.36, 0.36, -0.12]}
  />

  <!-- Lavender -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.36, -0.24]}
  />

  <!-- Copper -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.36, -0.12]}
  />

  <!-- Strawberry -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.36, 0]}
  />

  <!-- Baby Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.36, 0.12]}
  />

  <!-- Mauve -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.36, 0.24]}
  />

  <!-- Cool White -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.36, 0.24]}
  />

  <!-- Gross Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.36, 0.24]}
    rotation={[spinX, 0, 0]}
  />

  <!-- Weird Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.36, 0.24]}
  />

  <!-- Deep Red -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.36, 0.24]}
  />

  
  <!-- Royal Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.36, 0.12]}
  />

  <!-- Rose -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.36, 0.12]}
  />

  <!-- Orange -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.36, 0]}
  />

  <!-- Purple -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.36, 0]}
  />

  <!-- Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.36, 0.12]}
  />

  <!-- Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.36, -0.12]}
  />

  <!-- Limestone -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: m
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.36, -0.24 - j]}
  />

  <!-- Green -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.36, 0]}
  />

  <!-- Mint -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.36, 0]}
  />

  <!-- 

    ************
    Third Layer 
    ************
  
  -->

  <!-- Dark Grey -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: m
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.24 - j * 0.5, -0.24]}
  />

  <!-- Aqua -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.24, -0.12]}
  />

  <!-- Grey -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.24, -0.12]}
  />

  <!-- Black -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.24, -0.24]}
  />

  <!-- Red -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.24, -0.12]}
  />

  <!-- Lime -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.24, 0.12]}
  />

  <!-- Copper -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.24, -0.24]}
  />

  <!-- Copper -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.24, -0.12]}
  />

  <!-- Copper -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.36, 0.24, -0.12]}
    rotation={[0, spinX, 0]}
  />

  <!-- Strawberry -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.24, 0]}
  />

  <!-- Strawberry -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.36, 0.24, 0]}
  />

  <!-- Baby Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.24, 0.24]}
    rotation={[spinX, 0, 0]}
  />

  <!-- Baby Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.24, 0.12]}
  />

  <!-- Baby Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.36, 0.24, 0.12]}
  />

  <!-- Cool White -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.24, 0.24]}
  />

  <!-- Gross Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.24, 0.24]}
  />

  <!-- Weird Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.24, 0.24]}
  />

  <!-- Royal Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.24, 0.12]}
  />

  <!-- Rose -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.24, 0.12]}
  />

  <!-- Orange -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.24, 0]}
  />

  <!-- Purple -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.24, 0]}
  />

  <!-- Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.24, 0.12]}
  />

  <!-- Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.24, -0.12]}
  />

  <!-- Limestone -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.24, -0.24]}
  />

  <!-- Green -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.24, 0.24, 0]}
  />

  <!-- Mint -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.24, 0]}
  />

  <!-- 

    ************
    Second Layer 
    ************
  
  -->

  

  <!-- Red -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.12, -0.12]}
  />

  <!-- Red -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.12, -0.12]}
  />

  <!-- Lime -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.12, 0.12]}
  />

  <!-- Lime -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.12, 0.12]}
  />

  

  <!-- Orange -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0.12, 0]}
  />

  <!-- Orange -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.24, 0.12, 0]}
  />

  <!-- Purple -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0x870391,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.12, 0]}
  />

  <!-- Blue -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.12, 0.12]}
  />

  <!-- Yellow -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0, 0.12, -0.12]}
  />

  <!-- Mint -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[-0.12, 0.12, 0]}
    rotation={[spinX, 0, 0]}
  />

  <!-- 

    ************
    Base Layer 
    ************

  -->

  <!-- Purple -->
  <SC.Mesh
    geometry={new THREE.BoxGeometry()}
    material={new THREE.MeshStandardMaterial(
      { 
        color: 0xb000bd,
        transparent: true,
        opacity: 0.85,
        emissive: 0x1800cc,
        roughness: 0.57,
        metalness: 0
      }
    )}
    scale={[0.1, 0.1, 0.1]}
    castShadow
    position={[0.12, 0, 0]}
    rotation={[0, spinX, 0]}
  />


	<SC.PerspectiveCamera position={[-0.7, 1, 2.5]} />
	<SC.OrbitControls enableZoom={false} maxPolarAngle={Math.PI * 0.51} autoRotate={true} />
	<SC.AmbientLight intensity={0.6} />
	<SC.DirectionalLight intensity={0.6} position={[-2, 3, 2]} shadow={{ mapSize: [2048, 2048] }} />
</SC.Canvas>

<style>

</style>
