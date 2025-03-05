<script lang="ts">
    import Navbar from '$lib/navbar.svelte'
    import Card from '$lib/card.svelte'
    import bubbles from '../../assets/bubbles.jpeg'
    
    let contentsElems = {};

    function initializeScrollObserver() {
        document.querySelectorAll('#table-of-contentsElems a').forEach(elem => {
            contentsElems[elem.hash] = elem;
        });

        const options = {
            threshold: [0, .1, .2, .3, .4, .5, .6, .7, .8, .9, 1],
        };
        let scrollObserver = new IntersectionObserver(onIntersection, options);
        document.querySelectorAll('.section').forEach(e => scrollObserver.observe(e));
    }
    function onLoad() {
        initializeScrollObserver();
    }
    function onIntersection(entries, observer) {
        entries.forEach(e => {
            if (e.isIntersecting) {
                let link = contentsElems['#' + e.target.id];
                if (! link) {
                    console.warn(`label not found ${e.target.id}`);
                    return
                }
                if (e.intersectionRatio > 0.4) {
                    link.classList.add('selected');
                } else {
                    link.classList.remove('selected');
                }
            }
        });
    }

</script>


<style>
    .section {
        border-radius: 15px;
        overflow-y: hidden;
        background-color: lightgray;
        padding: 1rem 2rem;
        margin-bottom: 2rem;
        scroll-margin-top: 5rem;
    }
    :global(body.dark) .section {
        background-color: #0e1724;
    }
    .section h2 {
        font-size: 2.25rem;
        font-weight: bold;
        margin-bottom: 1rem;
    }
    .section:target h2 {
        text-decoration: underline;
    }
    .selected {
        font-weight: bold;
    }

    :global(body) {
        background-color: #EEEEEE;
        transition: background-color 0.3s
    }
    :global(body.dark) {
        background-color: #242529;
    }
</style>


<Navbar />

<div class="container mx-auto flex flex-col lg:flex-row">


    <!-- Table of Contents -->
    <div id="table-of-contentsElems" class="w-full lg:w-auto p-5 my-5 border rounded-xl border-gray-600 lg:fixed
        bg-white dark:bg-gray-800
        text-gray-500 dark:text-gray-300
        ">
        <h2 class="text-xl font-bold mb-4
            text-gray-700 dark:text-gray-400"
        >Contents</h2>
        <ul class="space-y-2 px-5">
            <li><a href="#about" class="hover:font-bold">About</a></li>
        </ul>
    </div>

    <!-- Content -->
    <div use:onLoad id="content-area" class="w-full lg:w-auto lg:ml-[15%]
        text-gray-600 dark:text-gray-300">
        <!-- ABOUT -->
        <div id="about" class="section">
            <h2> About Me </h2>
            <img src={bubbles} alt="gettin lit off de bubbles" />
            <p class="text-xl pb-1 dark:text-gray-200">
                I go by Sam around friends and Mr. Thomas around state apparatchiks, authority figures, and the like.
            
                I am a PhD student and Graduate TA at the
                <a class="text-blue-700 hover:underline" href="https://philosophy.arizona.edu/person/samuel-thomas"
                >University of Arizona</a>. 
                </p> <p class="text-xl py-1">
                My present research interests revolve around applied political philosophy. Specifically, I am interested in what we should do to prevent or reverse democratic backsliding, what ethical limits there are on economic sanctions, and which types of political compromises are unjust. I have also written on the concept of ideology.
                
                Before coming to the University of Arizona, I graduated from Arizona State University with a B.A. in Philosophy and Italian in 2019 and an M.A. in Philosophy in 2021. My M.A. thesis dealt with legal epistemology, specifically how judges and juries should evaluate different types of evidence. However, my interests have shifted a fair bit over the last couple years. Aside from my academic commitments, I am part of the Editorial Board for the 
                <a class="text-blue-700 hover:underline" href="https://ctwgwebsite.github.io"
                >Critical Theory Working Group</a>. 
                </p> <p class="text-xl py-1">
            </p>
        </div>
    </div>
</div>
