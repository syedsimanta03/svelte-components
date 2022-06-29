<script>
	import { slide } from "svelte/transition";
	export let entry = []
	let isOpen = false
	const toggle = () => isOpen = !isOpen
</script>

  <h2 id="accordion-open-heading-1">
    <button on:click={toggle} type="button" class="flex justify-between items-center p-5 w-full font-medium text-left border border-b-0 border-gray-200 focus:ring-4 focus:ring-gray-200 focus:ring-gray-800 border-gray-700 hover:bg-gray-100 hover:bg-gray-800 bg-gray-100 bg-gray-800 text-gray-900 text-white" data-accordion-target="#accordion-open-body-1" aria-expanded="true" aria-controls="accordion-open-body-1">
      <span class="flex items-center"><svg class="mr-2 w-5 h-5 shrink-0" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-8-3a1 1 0 00-.867.5 1 1 0 11-1.731-1A3 3 0 0113 8a3.001 3.001 0 01-2 2.83V11a1 1 0 11-2 0v-1a1 1 0 011-1 1 1 0 100-2zm0 8a1 1 0 100-2 1 1 0 000 2z" clip-rule="evenodd"></path></svg>{entry.ques}</span>
      <svg class="w-6 h-6 {isOpen ? 'rotate-180': 'rotate-0'} shrink-0" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
    </button>
  </h2>

{#if isOpen}
<ul transition:slide={{ duration: 300 }}>
    <div class="p-5 border border-b-0 border-gray-200 border-gray-700 bg-gray-900">
      <p class="mb-2 text-gray-500 text-gray-400">{entry.text}</p>
    </div>
  </ul>
{/if}
