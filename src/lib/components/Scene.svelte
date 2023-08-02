<script lang="ts">
	// noinspection ES6UnusedImports
	import { T } from '@threlte/core';
	import { Float, Grid, OrbitControls } from '@threlte/extras';
	import { DoubleSide } from 'three';
</script>

<T.PerspectiveCamera fov={15} makeDefault position={[-10, 10, 10]}>
	<OrbitControls autoRotate autoRotateSpeed={0.5} enableDamping enableZoom={false} target.y={1.5} />
</T.PerspectiveCamera>

<T.DirectionalLight intensity={0.8} position.x={5} position.y={10} />
<T.AmbientLight intensity={0.2} />

<Grid
	cellColor="#ffffff"
	cellSize={2}
	fadeDistance={25}
	position.y={-0.001}
	sectionColor="#ffffff"
	sectionThickness={0}
>
	<T.Mesh rotation.x={-Math.PI / 2} position={[0, 0, 0]}>
		<T.PlaneGeometry args={[5, 5]} />
		<T.MeshStandardMaterial color="blue" side={DoubleSide} />
	</T.Mesh>
</Grid>

<Float floatIntensity={1} floatingRange={[0, 1]}>
	<T.Mesh position.y={1.2} position.z={-0.75}>
		<T.BoxGeometry />
		<T.MeshStandardMaterial color="#0059BA" />
	</T.Mesh>
</Float>

<Float floatIntensity={1} floatingRange={[0, 1]}>
	<T.Mesh position={[1.2, 1.5, 0.75]} rotation.x={5} rotation.y={71}>
		<T.TorusKnotGeometry args={[0.5, 0.15, 100, 12, 2, 3]} />
		<T.MeshStandardMaterial color="#F85122" />
	</T.Mesh>
</Float>

<Float floatIntensity={1} floatingRange={[0, 1]}>
	<T.Mesh position={[-1.4, 1.5, 0.75]} rotation={[-5, 128, 10]}>
		<T.IcosahedronGeometry />
		<T.MeshStandardMaterial color="#F8EBCE" />
	</T.Mesh>
</Float>
