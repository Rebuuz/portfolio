<script lang="ts">
    let isOpen = false;
</script>

<header class="navbar-section sticky top-5 z-50 mx-auto mt-4
        w-full sm:w-[92%] lg:w-[80%]
        rounded-2xl lg:rounded-full
        bg-white border-none shadow-xl
        p-4 md:w-md">
    <div class="navbar-items mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-start md:justify-center gap-10 h16 items-center">
            <!--desktop menu-->
            <div class="hidden md:flex space-x-8">
                <a href="#home" class="hover-underline hover:text-secondary transition" aria-label="home">home</a>
                <a href="#aboutme" class="hover-underline scroll-mt-32 hover:text-secondary transition" aria-label="about me">about me</a>
                <a href="#projects" class="hover-underline hover:text-secondary transition" aria-label="projects">projects</a>
                <a href="#contact" class="hover-underline hover:text-secondary transition" aria-label="projects">contact</a>
            </div>

            <!--mobile menu-->
            <button class="md:hidden focus:outline-none" on:click={() => (isOpen = !isOpen)}>
                {#if isOpen}
                ✖
                {:else}
                ☰
                {/if}
            </button>
        </div>
    </div>
    <!--mobile menu items-->
    {#if isOpen}
        <div class="md:hidden bg-white px-4 pb-4 space-y-2">
            <a href="#home" class="block hover:text-secondary transition" aria-label="home">home</a>
            <a href="#hero-section" class="block hover:text-secondary transition" aria-label="about me">about me</a>
            <a href="#hero-section" class="block hover:text-secondary transition" aria-label="projects">projects</a>
        </div>
    {/if}
</header>
