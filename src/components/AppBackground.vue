<template lang="">
  <div></div>
</template>
<script>
import * as THREE from "three";
import TWEEN from "@tweenjs/tween.js";
export default {
  mounted() {
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(
      75,
      window.innerWidth / window.innerHeight,
      0.1,
      1000
    );
    camera.position.z = 5;

    const renderer = new THREE.WebGLRenderer();
    renderer.setSize(window.innerWidth, window.innerHeight);
    document.body.appendChild(renderer.domElement);
    renderer.setClearColor("#fc92c6");

    window.addEventListener("resize", () => {
      renderer.setSize(window.innerWidth, window.innerHeight);
      camera.aspect = window.innerWidth / window.innerHeight;
      camera.updateProjectionMatrix();
    });

    const box = new THREE.BoxGeometry(1, 1, 1.5);
    const material = new THREE.MeshLambertMaterial({ color: "#fff" });
    //
    const positions = {
      x: [-7, 10, -1, 5, -3, 3, -2, -10, -3, 2, 2, -3, 6, 4, -4],
      y: [-2, -2, -3, -4, 3, 3, -2, 2, 3, 0, -3, 0, 4, 2, 0],
      z: [-0.3, -2, -7, -9, -3, 1, 1, -11, 1, 2, 1, -20, -30, -4, 1],
      delay: [
        100,
        200,
        300,
        100,
        500,
        250,
        120,
        452,
        120,
        30,
        221,
        90,
        300,
        400,
        500,
      ],
    };

    for (let i = 0; i < 15; i++) {
      const mesh = new THREE.Mesh(box, material);
      mesh.position.x = positions.x[i];
      mesh.position.y = positions.y[i];
      mesh.position.z = positions.z[i];
      var tween = new TWEEN.Tween(mesh.position)
        .to({ y: positions.y[i] + 0.05 }, 750)
        .repeat(Infinity)
        .delay(positions.delay[i])
        .yoyo(true)
        .easing(TWEEN.Easing.Cubic.InOut)
        .start();
      tween.repeat(Infinity);
      scene.add(mesh);
    }

    const light = new THREE.PointLight(0xffffff, 1, 300);
    light.position.set(1, 0, 0);
    scene.add(light);

    const light2 = new THREE.PointLight(0xffffff, 1, 300);
    light2.position.set(0, 10, 25);
    scene.add(light2);

    const animate = () => {
      requestAnimationFrame(animate);
      TWEEN.update();
      renderer.render(scene, camera);
    };

    animate();
  },
};
</script>
<style lang=""></style>
