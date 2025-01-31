<script lang="ts">
    import logo from '../assets/sam1_.png'
    import '@fortawesome/fontawesome-free/css/all.min.css'
</script>

<div class="mt-14 lg:mt-24">

    <!-- Navbar -->
    <nav class="flex justify-around py-4 bg-black/80 py-2 backdrop-blur-md w-full fixed top-0 left-0 right-0 z-10">

        <!-- Logo Container -->
        <div class="flex items-center">
            <!-- Logo -->
            <a class="cursor-pointer">
                <img class="h-10 object-cover"
                    src={logo} alt="sam thomas headshot">
                </a>
            </div>

            <!-- Links Section -->
            <div class="items-center p-2">
                <a class="text-gray-200 cursor-pointer text-2xl">
                    Sam Thomas
                </a>

            </div>

            <!-- Icon Menu Section -->
            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex cursor-pointer hover:text-blue-500 transition-colors duration-200" href="bluesky.app" >
                    <i class="fa-brands fa-bluesky"></i>
                </a>

                <a class="flex hover:text-blue-500 transition-colors duration-200" href="x.com/xkcd" >
                    <i class="fa-brands fa-x-twitter"></i>
                </a>

                <a class="flex hover:text-blue-500 transition-colors duration-200" href="mailto@todo" >
                    <i class="fa-regular fa-envelope"></i>
                </a>

                <span class="pl-5">
                    <a class="hover:text-blue-500 cursor-pointer transition-colors duration-200 " >
                        <i class="fa-solid fa-sun"></i>
                    </a>
                    /
                    <a class="hover:text-blue-500 cursor-pointer transition-colors duration-200" >
                        <i class="fa-solid fa-moon"></i>
                    </a>
                </span>
            </div>
        </nav>
    </div>

