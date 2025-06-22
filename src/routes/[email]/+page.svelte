<script lang="ts">
	import { page } from '$app/state';
	import Card from '@/components/ui/card.svelte';

  let pageName = $derived(page.params.email);
</script>


<h1 class="text-3xl">{pageName}'s Page</h1>
<ul class="flex gap-6">
  <li><Card></Card></li>
  <li><Card></Card></li>
  <li><Card></Card></li>
</ul>
