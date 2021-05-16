<script lang="ts">
	import '@spectrum-css/vars/dist/spectrum-global.css';
	import '@spectrum-css/vars/dist/spectrum-medium.css';
	import '@spectrum-css/vars/dist/spectrum-darkest.css';
	import '@spectrum-css/vars/dist/spectrum-dark.css';
	import '@spectrum-css/vars/dist/spectrum-light.css';
	import '@spectrum-css/vars/dist/spectrum-lightest.css';
	import '@spectrum-css/page/dist/index-vars.css';

	import { Button, ActionMenu } from '$lib/bbui';
	import loadSpectrumIcons from '$lib/bbui/spectrum-icons-vite.js';
import ComponentSelectionList from '$lib/builder/AppPreview/ComponentSelectionList.svelte';
	loadSpectrumIcons();

</script>

<svelte:head>
	<title>Builder</title>
</svelte:head>

<div class="root">
	<div class="ui-nav">
		<!-- <FrontendNavigatePane /> -->
		FrontendNavigatePane
	</div>

	<div class="preview-pane">
		<!-- {#if $currentAsset} -->
		<ComponentSelectionList />
		
		<div class="preview-content">
			<!-- <CurrentItemPreview /> -->
			CurrentItemPreview
		</div>
		<!-- {/if} -->
	</div>

	<!-- {#if $selectedComponent != null} -->
	<div class="components-pane">
		<!-- <PropertiesPanel /> -->
		PropertiesPanel
	</div>
	<!-- {/if} -->
</div>

<style>
	.root {
		display: grid;
		grid-template-columns: 260px 1fr 260px;
		align-items: stretch;
		flex: 1 1 auto;
		height: 0;
	}

	.ui-nav {
		grid-column: 1;
		background-color: var(--background);
		display: flex;
		flex-direction: column;
		gap: var(--spacing-l);
		padding: 0 0 60px 0;
		overflow-y: auto;
		border-right: var(--border-light);
	}

	.preview-pane {
		grid-column: 2;
		overflow-y: auto;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: stretch;
		gap: var(--spacing-l);
		padding: var(--spacing-l) 40px var(--spacing-xl) 40px;
	}
	.preview-content {
		background: var(--background);
		box-shadow: 0 0 12px rgba(0, 0, 0, 0.05);
		flex: 1 1 auto;
	}

	.components-pane {
		grid-column: 3;
		background-color: var(--background);
		overflow-y: auto;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: stretch;
		border-left: var(--border-light);
		overflow-x: hidden;
	}

</style>
