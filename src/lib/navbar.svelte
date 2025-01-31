<script lang="ts">
    import logo from '../assets/sam1_.png'
    import '@fortawesome/fontawesome-free/css/all.min.css'
</script>

<div class="mt-14 lg:mt-24">

    <!-- Navbar -->
    <nav class="flex justify-around py-4 bg-black/80 py-2 backdrop-blur-md w-full fixed top-0 left-0 right-0 z-10">

        <div class="flex items-center">
            <!-- Left -->
            <a class="cursor-pointer">
                <img class="h-10 object-cover" href="/" src={logo} alt="sam thomas headshot">
                </a>
            </div>

            <!-- Middle -->
            <div class="items-center p-2">
                <a class="text-gray-200 cursor-pointer text-2xl" href="/">
                    Sam Thomas
                </a>
            </div>

            <!-- Right -->
            <div class="flex items-center space-x-5 text-gray-300 ">
                <a class="flex cursor-pointer hover:text-blue-500 transition-colors duration-200"
                    href="https://bsky.app/profile/wokesteppenomad.bsky.social" >
                    <i class="fa-brands fa-bluesky"></i>
                </a>

                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="https://x.com/wokesteppenomad/" >
                    <i class="fa-brands fa-x-twitter"></i>
                </a>

                <a class="flex hover:text-blue-500 transition-colors duration-200"
                    href="mailto@samthomas@arizona.edu" >
                    <i class="fa-regular fa-envelope"></i>
                </a>

                <!-- Light/Dark -->
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

