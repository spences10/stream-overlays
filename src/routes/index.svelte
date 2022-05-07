<script lang="ts">
	import { page } from '$app/stores';

	export let title: string = $page.url.searchParams.get('title')?.toString() || 'Stream Overlay';
	export let details: string =
		$page.url.searchParams.get('details')?.toString() || 'Stream Overlay Details';
</script>

<section class="absolute bottom-0 p-10 border-2 border-primary w-3/5 rounded-xl mb-8 ml-8">
	<h1 class="text-5xl leading-relaxed tracking-wide text-shadow shadow-secondary">{title}</h1>
	<p class="text-3xl leading-relaxed tracking-wide text-shadow shadow-secondary">{details}</p>
</section>
