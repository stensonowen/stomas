<script lang="ts">
    import Navbar from '$lib/navbar.svelte'
    import Card from '$lib/card.svelte'
    import bent from '../assets/bent2.png'
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
        margin-bottom: 1rem;
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
            <Card
                publisher="Cosmonaut Mag"
                title="The Machiavellian State, Fascism, and the Tribune of the Proletariat"
                href="example.com"
                date="April 29, 2022"
                text="How Machiavelli can help us understand the bourgeois nature of fascism, and how anti-fascism must empower the proletariat"
            />
            <Card
                publisher="CTWG"
                title="On the Falsity of Prevailing Ideas: The Concept of Ideology in Early Critical Theory"
                href="https://ctwgwebsite.github.io/projects/1_project/"
                date="Fall 2024"
                text="Writers have spilled rivers of ink over the term “ideology.” This steady flow has become a deluge of mediocre tomes from uninquisitive minds..."
            />
        </div>

        <div id="section1" class="mb-8">

            <h2 class="text-4xl font-bold mb-4"> About </h2>

            <p class="text-xl text-gray-700">
            </p>
        </div>
    </div>

</div>

