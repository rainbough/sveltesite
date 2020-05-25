<script>
import router, { curRoute } from './router.js';
import RouterLink from './RouterLink.svelte';
import HeaderSection from './HeaderSection.svelte';
import { onMount } from 'svelte';
onMount(() => {
//   curRoute.set(window.location.pathname);
//   if (!history.state) {
//     window.history.replaceState({path: window.location.pathname}, '',   window.location.href)
//   }
})
function handlerBackNavigation(event){
//   curRoute.set(event.state.path)
}
</script>
<style>
    :root {
		
	}
    :global(body) {
		background: #222;
		color: #fff;
	}

</style>
<svelte:window on:popstate={handlerBackNavigation} />
<header role="banner">
	<HeaderSection>
		<nav>
			<RouterLink page={{path: '/home', name: 'Home'}} />
			<RouterLink page={{path: '/about', name: 'About'}} />
		</nav>
	</HeaderSection>
</header>
<main>
	<div id="pageContent">


	<!-- Page component updates here -->
	<svelte:component this={router[$curRoute]} />
	</div>
</main>
<footer role="contentinfo">
	<div class="footer-content">
		<h2>Footer Content here</h2>
	</div>
</footer>
