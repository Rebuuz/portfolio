<script lang="ts">
    let isOpen = false;
</script>

<nav class="navbar-section fixed top-0 w-full bg-white shadow-md shadow-rose-300/10 z-50 text-black h-10">
    <div class="navbar-items max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex mjustify-start md:justify-center gap-10 h16 items-center">
            <!--desktop menu-->
            <div class="hidden md:flex space-x-8">
                <a href="#hero-section" class="hover:text-red-300 transition" aria-label="home">home</a>
                <a href="#about-me" class="hover:text-red-300 transition" aria-label="about me">about me</a>
                <a href="#projects" class="hover:text-red-300 transition" aria-label="projects">projects</a>
                <a href="#contact" class="hover:text-red-300 transition" aria-label="projects">contact</a>
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
            <a href="#hero-section" class="block hover:text-red-300 transition" aria-label="home">home</a>
            <a href="#hero-section" class="block hover:text-red-300 transition" aria-label="about me">about me</a>
            <a href="#hero-section" class="block hover:text-red-300 transition" aria-label="projects">projects</a>
        </div>
    {/if}
</nav>

<style>
    .navbar-items {
        padding-top: .5rem;
        font-family: 'Poppins', sans-serif;
    }
</style>