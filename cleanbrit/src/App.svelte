<script>

	import Navbar from './components/menu/Navbar.svelte'
	import Sidebar from './components/menu/Sidebar.svelte'
	import Main from './components/menu/Main.svelte'

	import MC_main from './components/main_content/MC_main.svelte'


	let open = false
</script>

<Sidebar bind:open/>
<Navbar bind:sidebar={open}/>
<Main/>

<MC_main></MC_main>

<svelte:head>
	<link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet"/>
</svelte:head>

<style>
	:global(body) {
		padding: 0;
	}
</style>