<script>
	import Header from "./components/header.svelte";
	import Tabs from "./components/shared/tabs.svelte";
	import Bio from "./components/bio.svelte";
	//tabs
	let items = ["About", "Experience", "Skills", "Resume", "Contact"];
	let activeItem = "About";
	const tabChange = (e) => {
		activeItem = e.detail;
	};
</script>

<Header />
<main>
	<Tabs {activeItem} {items} on:tabChange={tabChange} />
	{#if activeItem === "About"}
		<Bio />
	{:else if activeItem === "Experience"}
		<p>Experience</p>
	{:else if activeItem === "Skills"}
		<p>Skills</p>
	{:else if activeItem === "Resume"}
		<p>
			<a href="./sample.pdf" target="_blank">Resume</a>
		</p>
	{:else if activeItem === "Contact"}
		<p>Contact</p>
	{/if}
</main>

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>
