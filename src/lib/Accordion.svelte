<script>
	import AccordionItem from './AccordionItem.svelte'
  
	const data = [
		{ques:'Question Item 1', text:'who is that1'},
		{ques:'Question Item 12', text:'who is that2'},
		{ques:'Question Item 13', text:'who is that3'},
	]

</script>

{#each data as entry}
<AccordionItem {entry} />
{/each}
