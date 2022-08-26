<script lang="ts">
	import { page } from '$app/stores';
	import { GenericEmbed } from 'sveltekit-embed';

	let title: string = $page.url.searchParams.get('title')?.toString() || 'Stream Overlay';
	let details: string =
		$page.url.searchParams.get('details')?.toString() || 'Stream Overlay Details';
	let sessionId: string = $page.url.searchParams.get('sessionId')?.toString() || 'BRZQF8gbvd';
</script>

<section
	class="absolute bottom-0 right-0 border-2 border-primary w-4/12 rounded-xl mb-8 mr-10 overflow-hidden p-4 h-52"
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

<section class="absolute bottom-0 p-10 border-2 border-primary w-3/5 rounded-xl mb-8 ml-10 h-52">
	<h1 class="text-5xl leading-relaxed tracking-wide text-shadow shadow-secondary">{title}</h1>
	<p class="text-3xl leading-relaxed tracking-wide text-shadow shadow-secondary">{details}</p>
</section>
