<script lang="ts">
    import '@fortawesome/fontawesome-free/css/all.min.css'
    let pr = $props();
</script>

<div class="container text-xl p-2 rounded-r-xl mb-5
    bg-gray-100 dark:bg-black
    ">
    <a class="text-3xl p-1" href={pr.link}>
        {#if pr.publisher}
            <span class="text-gray-600 italic pr-2"> {pr.publisher}: </span>
        {/if}
        <span class="text-gray-800"> {pr.title} </span>
    </a>
    <p class="pt-1">
        {#if pr.date}
            <span class="text-gray-500 pr-2"> {pr.date} </span>
        {/if}
        {#if pr.audio}
            <i class="fa-solid fa-volume-low"></i>
        {/if}
        {#if pr.pdf}
            <a href={pr.pdf}><i class="fa-solid fa-file-pdf"></i></a>
        {/if}
        {#if pr.creativecommons}
            <i class="fa-brands fa-creative-commons"></i>
            <i class="fa-brands {pr.creativecommons}"></i>
        {/if}
        <span class="pl-2"> {pr.text} </span>
    </p>
</div>
