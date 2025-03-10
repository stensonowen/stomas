<script lang="ts">
    import Navbar from '$lib/navbar.svelte'
    import Card from '$lib/card.svelte'
    
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
            <li><a href="#teaching_self" class="hover:font-bold">Courses Taught (as Instructor of Record)</a></li>
            <li><a href="#teaching_other" class="hover:font-bold">Courses Taught (as Gradute Teacher's Assistant)</a></li>
            <li><a href="#grading" class="hover:font-bold">Graderships</a></li>    
        </ul>
    </div>

    <!-- Content -->
    <div use:onLoad id="content-area" class="w-full lg:w-auto lg:ml-[15%]
        text-gray-600 dark:text-gray-300">
        <div id="teaching_self" class="section">
            <h2> Courses Taught (as Instructor of Record) </h2>
            <Card
                title="PHIL265 - Twentieth Century Continental Philosophy"
                date="Fall 2024"
                text="The twentieth century saw massive changes in sociopolitical organization, technology, and social mores. In this course, students will examine with different philosophical perspectives on these shifts, and engage with topics such as the relationship between the State and civil society, the limits of the law in constraining the State, the way that new technological developments shape our relation to the world, and how we should act in a world that had lost faith in God."
            /> 
            <Card
                title="PHIL323 - Environmental Ethics"
                date="Summer 2024"
                text="We will investigate and seriously consider how and why we should live as morally responsible members of an ecological community. Students will explore philosophical responses to questions such as: What makes something natural? What value is there to non-human entities? What obligations do we have to each other regarding the environment? Students will investigate social scientific responses to questions such as: How should wilderness be preserved? How should we respond to climate change? How should water resources be allocated? Students will build connections between and reconcile philosophical and social scientific approaches to issues of environmental concern."
            /> 
            <Card
                title="PHIL263 - From Hegel to Nietzsche: 19th Century Philosophy"
                date="Spring 2024, Spring 2025"
                text="Survey of influential 19th century philosophers, including Hegel, Marx, J. S. Mill, Kierkegaard, and Nietzsche. Their views on the individual and society, and human nature."
            />
            <Card
                title="PHIL246 - Existentialism and Phenomenology"
                date="Summer 2023"
                text="Suppose it was entirely up to you to decide what is right or wrong, what is valuable and what is not. Suppose it was entirely up to you in the sense that there were no other standards or guidelines to tell you how to go about making these decisions. That would be a huge and perhaps scary task. Is it even possible to make decisions in a world where there are no objective norms and values to fall back on? A group of philosophers, the existentialists, thought that our actual task in this world is not so different. On their account, at least when it comes to what is most valuable and the fundamental norms of one's own life, it is entirely up to each one of us to make that decision for ourselves. This course is an introduction to various theories and expressions of 19th- and 20th-century existentialism and its phenomenological method. We will read authors such as Kierkegaard, Nietzsche, Husserl, Sartre, Camus, de Beauvoir, and Fanon. We will also analyze some existentialist literature."
            />
        </div>
        <div id="teaching_other" class="section">
            <h2> Courses Taught (as Graduate Teacher's Assistant) </h2>
            <Card
                title="PHIL160D1 - Justice and the good life (with Prof. Houston Smit)"
                date="Spring 2023, Fall 2023"
                text="We all want to live good lives. To have a good life, in the sense I have in mind, is to be happy, where `happiness' is understood in something like the sense in which the Declaration of Independence proclaims that we each have an inalienable right to the pursuit of happiness. But what is it to live a good life? What is it to be happy? To the extent that the kind of life you live is up to you, this is a pressing question. If you take the question seriously, others soon follow. To what extent is it up to me whether or not my life is a good one? It's tempting to think that moral obligations can conflict with your living a good life, so that you have to choose between doing what is right and doing what would make you happy. But can such conflicts arise? And, if so, which should one choose? How, if at all, does your ability to live a good life depend on the particular society in which you live? These, and other questions about justice and the good life, have long occupied philosophers. In this course, we will, together, explore these questions, drawing on what four great philosophers have to say about them: Plato, Aristotle, Kant, and Mill."
            /> 
        </div>
        <div id="grading" class="section">
            <h2> Graderships </h2>
            <Card
                title="PHIL160D1 - Justice and the good life"
                date="Spring 2025"
                text="As above."
            />
            <Card
                title="PHIL150C1 - Freedom, Equality, Authority"
                date="Spring 2025"
                text="This course examines fundamental questions about the ethical organization of society and social life. These questions include: What is the basis of the state? What is the nature of social justice? What are our obligations to others around the world? We will aim to develop clear thinking about issues that are of great importance to the contemporary world and that each of us will face as a citizen of a modern democratic state."
            /> 
            <Card
                title="PHIL324 - Law and Morality"
                date="Fall 2024"
                text="Exploration of classic and contemporary philosophical issues about law and morality. Topics covered will vary but may include, among others, the limits of social interference with individual liberty, legal paternalism and physician-assisted suicide, legal moralism, freedom of speech and expression, legal punishment and capital punishment, and civil disobedience."
            />              
        </div>
    </div>
</div>

