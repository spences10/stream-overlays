<script lang="ts">
	import { page } from '$app/stores';
	import { GenericEmbed } from 'sveltekit-embed';

	let title: string = $page.url.searchParams.get('title')?.toString() || 'Stream Overlay';
	let details: string =
		$page.url.searchParams.get('details')?.toString() || 'Stream Overlay Details';
	let sessionId: string = $page.url.searchParams.get('sessionId')?.toString() || 'BRZQF8gbvd';
</script>

<section class="absolute bottom-0 p-10 border-4 border-primary w-[75rem] rounded-xl mb-2 ml-2 h-52">
	<div class="prose prose-xl">
		<h1 class="text-5xl mb-4 tracking-wide text-shadow shadow-secondary">{title}</h1>
		<p class="text-3xl tracking-wide text-shadow shadow-secondary">{details}</p>
	</div>
</section>

<section
	class="absolute bottom-0 right-0 border-4 border-primary w-[43rem] rounded-xl mb-2 mr-2 overflow-hidden p-4 h-52"
>
	<GenericEmbed
		width="100%"
		height="175px"
		data-testid="spotify"
		title="social-stream-chat-overlay"
		src={`https://social-stream.vercel.app/dock.html?session=${sessionId}&hidesource&noavatar&notime&compact`}
		frameBorder="0"
		allow="encrypted-media"
		overflow="hidden"
		scrolling="no"
	/>
</section>
