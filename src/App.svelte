<script>
	import * as BABYLON from "@babylonjs/core/Legacy/legacy";
    import { onMount } from 'svelte';

	let canvas, engine, scene;

    onMount(() => {
        engine = new BABYLON.Engine(canvas, true);
        scene = new BABYLON.Scene(engine);

		// .... rest of your code
		const camera = new BABYLON.ArcRotateCamera("camera", -Math.PI / 2, Math.PI / 2.5, 3, new BABYLON.Vector3(0, 0, 0));
		camera.attachControl(canvas, true);

		const light = new BABYLON.HemisphericLight("light", new BABYLON.Vector3(0, 1, 0));

		const box = BABYLON.MeshBuilder.CreateBox("box", {});
	
			engine.runRenderLoop(function(){
				scene.render();
			});
		});

</script>


<canvas bind:this={canvas}/>


<style>
	canvas {
		width: 100%;
		height: 100%;
		display: block;
		font-size: 0;
	}
</style>