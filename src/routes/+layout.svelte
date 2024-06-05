<script>
	import '../app.postcss';
	let links = ["/Home","/Characters"]
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';

	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });




</script>




<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase">Unmatched Vault </strong>
				<strong class="text-xl uppercase"> {#each links as link}
					<a class = "headr" href={link}>{link.length<2?"Hem":link.charAt(1).toUpperCase()
				   + link.slice(2)}</a>
				 {/each}</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://unmatched.cards/umdb/sets"
					target="_blank"
					rel="noreferrer"
				>
					UmDb
				</a>
				
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>

<style>

.headr{
	
	font-size:large;
	padding-left: 10px;
	margin-left: 25px;
	opacity: 30%;
}

.headr:hover{
	color: rgb(168 162 158);
	opacity: 100%;
}

</style>