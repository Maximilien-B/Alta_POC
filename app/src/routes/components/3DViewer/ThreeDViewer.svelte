<script>
    import * as THREE from "three";

    export let ModelPath
    export let objectVector // (x,y,z) Scale, Y translation
    import { OrbitControls } from 'three/addons/controls/OrbitControls.js'
    import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js'
    import {onMount} from "svelte";

    onMount(() => {
        const container = document.getElementById('dviewer');

        const scene = new THREE.Scene();

        const aspect = container.clientWidth / container.clientHeight;
        var frustumSize = 10;
        const camera = new THREE.OrthographicCamera(
            frustumSize * aspect / -2,
            frustumSize * aspect / 2,
            frustumSize / 2,
            frustumSize / -2,
            0.1,
            5000
        );
        camera.position.set(50,50,1000)
        camera.lookAt(new THREE.Vector3(0,0,0));

        const renderer = new THREE.WebGLRenderer({ alpha: true});
        renderer.setSize(container.clientWidth, container.clientHeight);
        container.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera, renderer.domElement);
        controls.enableDamping = true;
        controls.dampingFactor = 0.05;
        controls.enableZoom = false;
        controls.enablePan = false;
        controls.minPolarAngle = Math.PI / 2;
        controls.maxPolarAngle = Math.PI / 2;

        const light1 = new THREE.DirectionalLight(0xffffff, 2);
        light1.position.set(5, 5, 5).normalize();
        const light2 = new THREE.DirectionalLight(0xffffff, 2);
        light2.position.set(-5, 5, 5).normalize();
        const light3 = new THREE.DirectionalLight(0xffffff, 2);
        light3.position.set(0, 0, -5).normalize();
        scene.add(light1);
        scene.add(light2);
        scene.add(light3);

        const loader = new GLTFLoader();
        let model;
        loader.load(ModelPath, function(gltf) {
            model = gltf.scene;
            scene.add(model);
            model.position.set(0, 0, 0)
            model.translateY(objectVector[3])
            model.scale.set(objectVector[0],objectVector[1],objectVector[2])
            camera.updateProjectionMatrix();
            renderer.capabilities.getMaxAnisotropy()
            animate();
        }, undefined, function(error) {
            console.error(error);
        });


        window.addEventListener('resize', function() {
            const aspect = container.clientWidth / container.clientHeight;
            camera.left = -frustumSize * aspect / 2;
            camera.right = frustumSize * aspect / 2;
            camera.top = frustumSize / 2;
            camera.bottom = -frustumSize / 2;
            camera.updateProjectionMatrix();
            renderer.setSize(container.clientWidth, container.clientHeight);
        });

        function animate() {
            requestAnimationFrame(animate);
            if (model && !controls.isDragging) {
                model.rotation.y += 0.001;
            }
            controls.update();
            renderer.render(scene, camera);
        }

        // Initial render
        animate();
    })

</script>

<section class="dviewer_container" id="dviewer">
</section>

