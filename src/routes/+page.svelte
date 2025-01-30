<script lang="ts">
    import Navbar from '$lib/navbar.svelte'
    import bent from '../assets/bent2.png'
    import Card from '../card.svelte'
</script>

<style>
    .section {
        color: black;
        border-radius: 15px;
        overflow-y: hidden;
        background-color: lightgray;
        padding: 2rem;
        margin-bottom: 1rem;
        scroll-margin-top: 5rem;
    }
    .section h2 {
        font-size: 2.25rem;
        font-weight: bold;
    }
</style>


<Navbar />

<div class="container mx-auto flex flex-col lg:flex-row">

    <!-- Table of Contents -->
    <div class="w-full lg:w-auto p-5 bg-white border rounded-xl border-gray-200 lg:fixed ">
        <h2 class="text-xl text-gray-700 font-bold mb-4">Contents</h2>
        <ul class="space-y-2 px-5">
            <li><a href="#about"        class="text-gray-500 hover:font-bold">About</a></li>
            <li><a href="#publications" class="text-gray-500 hover:font-bold">Publications</a></li>
            <li><a href="#courses"      class="text-gray-500 hover:font-bold">Courses</a></li>
            <li><a href="#section4" class="text-gray-500 hover:font-bold">Papers</a></li>
            <li><a href="#section5" class="text-gray-500 hover:font-bold">Links</a></li>
        </ul>
    </div>

    <!-- Content -->
    <div class="w-full lg:w-auto lg:ml-[15%] ">

        <!-- ABOUT -->
        <div id="about" class="section">
            <img class="w-1/5 float-left mr-4 mb-4 rounded-lg" src={bent} alt="a man crouches" />
            <h2> About Sam Thomas </h2>
            <p class="text-xl py-1">
                PhD student and Graduate TA at the University of Arizona. 
                </p> <p class="text-xl py-1">
                Research interests include legal epistemology, linguistics, critical theory, and European history.
            </p>
        </div>

        <!-- PUBLICATIONS -->
        <div id="publications" class="section">
            <h2> Publications </h2>
            <p class="text-xl text-gray-700">
                helo
            </p>
        </div>

        <div id="section1" class="mb-8">

            <img class="w-1/3 float-left mr-4 mb-4 rounded-lg" src={bent} />

            <h2 class="text-4xl font-bold mb-4"> About </h2>

            <p class="text-xl text-gray-700">
            </p>
        </div>
        <div id="section2" class="mb-8">
            <h2 class="text-2xl font-bold mb-4">Publications</h2>
            <p class="text-gray-700">
                <Card name="foo" />
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
        </div>
        <div id="section3" class="mb-8">
            <h2 class="text-2xl font-bold mb-4">Section 3</h2>
            <p class="text-gray-700">
                Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
            </p>
        </div>
        <div id="section4" class="mb-8">
            <h2 class="text-2xl font-bold mb-4">Section 4</h2>
            <p class="text-gray-700">
                Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            </p>
        </div>
    </div>

</div>

<div class="container mx-auto px-20">

    <div class="rounded-xl bg-gray-300">
        <h1 class="text-3xl p-8 "
        >About </h1>
        <img class="h-80" src={bent} />
    </div>

    <h1>Welcome to SvelteKit</h1>
    <p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

</div>
