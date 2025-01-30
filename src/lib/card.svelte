<script lang="ts">
    let pr = $props();
</script>

<div class="container bg-gray-100 text-xl p-2 rounded-r-xl mb-5">
    <span class="text-3xl p-2">
        {#if pr.publisher}
            <span class="text-gray-600 italic pr-2"> {pr.publisher}: </span>
        {/if}
        <span class="text-gray-800"> {pr.title} </span>
    </span>
    <p class="pt-1">
        {#if pr.date}
            <span class="text-gray-500 pr-2"> {pr.date} | </span>
        {/if}
        <span> {pr.text} </span>
    </p>
</div>
