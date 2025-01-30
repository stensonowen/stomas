<script lang="ts">
    import logo from '../assets/sam1_.png'
    import bluesky from '../assets/Bluesky_Logo.svg'
    import logowebp from '../assets/sam1.webp'
    import email from '../assets/envelope-solid.svg'
</script>

<div class="flex flex-col items-center justify-center mt-32" >
    <div class="flex flex-col">

        <!-- Navbar -->
        <nav class="flex justify-around py-4 bg-black/80
            pt-2 pb-2
            backdrop-blur-md w-full
            fixed top-0 left-0 right-0 z-10">

            <!-- Logo Container -->
            <div class="flex items-center">
                <!-- Logo -->
                <a class="cursor-pointer">
                    <!--
                        <span class="flex text-gray-300 hover:text-blue-500 cursor-pointer transition-colors duration-300"
                        > Sam Thomas </span> -->
                        <img class="h-10 object-cover"
                            src={logo} >
                    </a>
                </div>

                <!-- Links Section -->
                <div class="items-center hidden space-x-8 lg:flex h20">
                    <a class="flex text-gray-300 cursor-pointer text-2xl">
                        Sam Thomas
                    </a>

                    <!--
                    <a class="flex text-gray-300 hover:text-blue-500
                        cursor-pointer transition-colors duration-300">
                        Themes
                    </a>
                    <a class="flex text-gray-300 hover:text-blue-500
                        cursor-pointer transition-colors duration-300">
                        Developers
                    </a>-->

                </div>

                <!-- Icon Menu Section -->
                <div class="flex items-center space-x-5">
                    <a class="flex text-gray-300 hover:text-blue-500 cursor-pointer transition-colors duration-300">
                        <img class="h-4 w-4 mr-2 mt-0.5" src={bluesky}>
                    </a>

                    <a class="flex text-gray-300 cursor-pointer transition-colors duration-300 font-semibold text-blue-600">
                        𝕏
                    </a>

                    <a class="flex text-white-300 hover:text-blue-500 cursor-pointer transition-colors duration-300">
                        <img class="h-4 w-4 mr-2 mt-0.5" src={email}>
                    </a>
                </div>
            </nav>
        </div>

    </div>

        <h1>Welcome to SvelteKit</h1>
        <p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>
