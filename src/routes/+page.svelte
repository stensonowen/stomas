<script lang="ts">
    import Navbar from '$lib/navbar.svelte'
    import Card from '$lib/card.svelte'
    import bent from '../assets/bent2.png'

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
            <li><a href="#about"        class="hover:font-bold selected">About</a></li>
            <li><a href="#publications" class="hover:font-bold">Publications</a></li>
            <li><a href="#courses"      class="hover:font-bold">Courses</a></li>
            <li><a href="#links"        class="hover:font-bold">Links</a></li>
        </ul>
    </div>

    <!-- Content -->
    <div use:onLoad id="content-area" class="w-full lg:w-auto lg:ml-[15%]
        text-gray-600 dark:text-gray-300">

        <!-- ABOUT -->
        <div id="about" class="section">
            <img class="w-1/5 float-left mr-4 mb-4 rounded-lg" src={bent} alt="a man crouches" />
            <h2> About Sam </h2>
            <p class="text-xl pb-1 dark:text-gray-200">
                PhD student and Graduate TA at the
                <a class="text-blue-700 hover:underline" href="https://philosophy.arizona.edu/person/samuel-thomas"
                >University of Arizona</a>. 
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
                link="https://cosmonautmag.com/2022/04/the-machiavellian-state-fascism-and-the-tribune-of-the-proletariat/"
                date="April 29, 2022"
                text="How Machiavelli can help us understand the bourgeois nature of fascism, and how anti-fascism must empower the proletariat"
                audio=true
            />
            <Card
                publisher="CTWG"
                title="On the Falsity of Prevailing Ideas: The Concept of Ideology in Early Critical Theory"
                link="https://ctwgwebsite.github.io/projects/1_project/"
                date="Fall 2024"
                text="Writers have spilled rivers of ink over the term “ideology.” This steady flow has become a deluge of mediocre tomes from uninquisitive minds..."
                pdf="https://ctwgwebsite.github.io/assets/pdf/journal/Margin_notes_1_final_full.pdf"
                creativecommons="fa-creative-commons-by"
            />
        </div>

        <!-- COURSES -->
        <div id="courses" class="section">
            <h2> Courses </h2>
            <Card
                title="PHIL246 - Existentialism and Phenomenology"
                date="Summer 2023"
                text="Suppose it was entirely up to you to decide what is right or wrong, what is valuable and what is not. Suppose it was \"entirely\" up to you in the sense that there were no other standards or guidelines to tell you how to go about making these decisions. That would be a huge and perhaps scary task. Is it even possible to make decisions in a world where there are no objective norms and values to fall back on? A group of philosophers, the existentialists, thought that our actual task in this world is not so different. On their account, at least when it comes to what is most valuable and the fundamental norms of one's own life, it is entirely up to each one of us to make that decision for ourselves. This course is an introduction to various theories and expressions of 19th- and 20th-century existentialism and its phenomenological method. We will read authors such as Kierkegaard, Nietzsche, Husserl, Sartre, Camus, de Beauvoir, and Fanon. We will also analyze some existentialist literature."
            />
        </div>

        <!-- LINKS -->
        <div id="links" class="section">
            <h2> Links </h2>
            <p> Soundcloud link, or montage of those albums you listen to on Fridays. Maybe embed a youtube video of playing Darude - Sandstorm on the guitar </p>
        </div>
    </div>

</div>

