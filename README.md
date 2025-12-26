// Load the suit model
const loader = new THREE.GLTFLoader();
loader.load('path/to/ironman_suit.glb', (gltf) => {
    const suit = gltf.scene;
    scene.add(suit);
    
    // Make the Arc Reactor glow!
    suit.traverse((child) => {
        if (child.name === "Arc_Reactor") {
            child.material.emissive = new THREE.Color(0x00ffff);
            child.material.emissiveIntensity = 2;
        }
    });
});
