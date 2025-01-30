<script lang="ts">
    import logo from '../assets/sam1_.png'
    import '@fortawesome/fontawesome-free/css/all.min.css'
</script>

<div class="flex flex-col mt-32">

    <!-- Navbar -->
    <nav class="flex justify-around py-4 bg-black/80
        pt-2 pb-2
        backdrop-blur-md w-full
        fixed top-0 left-0 right-0 z-10">

        <!-- Logo Container -->
        <div class="flex items-center">
            <!-- Logo -->
            <a class="cursor-pointer">
                <img class="h-10 object-cover"
                    src={logo} alt="sam thomas headshot">
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
                <a class="flex text-gray-300 hover:text-blue-500 cursor-pointer transition-colors duration-200"
                    href="bluesky.app" >
                    <i class="fa-brands fa-bluesky"></i>
                </a>

                <a class="flex text-gray-300 hover:text-blue-500 cursor-pointer transition-colors duration-200"
                    href="x.com/xkcd" >
                    <i class="fa-brands fa-x-twitter"></i>
                </a>

                <a class="flex text-gray-300 hover:text-blue-500 cursor-pointer transition-colors duration-200"
                    href="mailto@todo" >
                    <i class="fa-regular fa-envelope"></i>
                </a>
            </div>
        </nav>
    </div>

