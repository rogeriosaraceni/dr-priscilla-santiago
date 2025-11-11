<script lang="ts">
	import { page } from '$app/state';
</script>

<header class="flex justify-between bg-amber-700">
	<nav class="m-auto flex justify-center">
		<ul>
			<li aria-current={page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
		</ul>
	</nav>
</header>
