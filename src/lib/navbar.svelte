<script lang="ts">
    import logo from '../assets/sam1_.png'
    import { base } from '$app/paths';
    import '@fortawesome/fontawesome-free/css/all.min.css'

    function darken() {
        window.document.body.classList.add('dark');
    }
    function lighten() {
        window.document.body.classList.remove('dark');
    }

    function onLoad() {
        if (window.matchMedia('(prefers-color-scheme: dark)')) {
            console.log('browser requests dark mode');
            darken();
        }
    }
</script>

<style>
    #lighten { color: lightgray; }
    #darken  { color: gray; }
    :global(body.dark) #lighten { color: gray; }
    :global(body.dark) #darken  { color: lightgray; }

    #darken, #lighten {
      position: relative;
      display: inline-block;
      cursor: pointer;
    }

    #lighten::after { right: 0; }
    #darken::after  { left: 0; }

    #lighten::after,
    #darken::after {
      content: '';
      position: absolute;
      bottom: -2px;
      width: 0%;
      height: 2px;
      background-color: lightgray;
      transition: width 0.2s ease;
    }

    #lighten::after { width: 100%; }
    #darken::after { width: 0%; }
    :global(body.dark) #lighten::after { width: 0%; }
    :global(body.dark) #darken::after { width: 100%; }

</style>

<div class="mt-20 lg:mt-24">

    <!-- Navbar -->
    <nav use:onLoad={onLoad} class="flex justify-around py-4 bg-gray-700/80 dark:bg-gray-900/80 py-2 backdrop-blur-md w-full fixed top-0 left-0 right-0 z-10">

        <div class="flex items-center">
            <!-- Left -->
            <a class="cursor-pointer" href={`${base}/`}>
                <img class="h-10 object-cover" src={logo} alt="sam thomas headshot">
                </a>
            </div>

            <!-- Middle -->
            <div class="items-center p-2">
                <a class="text-gray-200 cursor-pointer text-2xl" href={`${base}/`}>
                    Samuel J. Thomas
                </a>
            </div>

            <!-- Right -->
            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="https://samueljthomasphilosophy.github.io/samueljthomas/about.html"> about
                </a>

            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="https://samueljthomasphilosophy.github.io/samueljthomas/research.html"> research
                </a>
            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="https://samueljthomasphilosophy.github.io/samueljthomas/teaching.html"> teaching
                </a>
            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="https://samueljthomasphilosophy.github.io/samueljthomas/ctwg.html"> ctwg
                </a>

            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="https://philpeople.org/profiles/samuel-j-thomas"> PhilPeople
                </a>

            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="mailto:samthomas@arizona.edu" aria-label="email link">
                    <i class="fa-regular fa-envelope"></i>
                </a>
                
                <!-- Light/Dark -->
                <span class="pl-5">
                    <button onclick={lighten} id="lighten" aria-label="light mode"
                        class="hover:text-blue-500 cursor-pointer transition-colors duration-200 " >
                        <i class="fa-solid fa-sun"></i>
                    </button>
                    /
                    <button onclick={darken} id="darken" aria-label="dark mode"
                        class="hover:text-blue-500 cursor-pointer transition-colors duration-200" >
                        <i class="fa-solid fa-moon"></i>
                    </button>
                </span>
            </div>
        </nav>
    </div>

