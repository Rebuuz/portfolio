<script lang="ts">
    import HeroComponent from "$lib/components/Hero.svelte";
    import AboutMe from "$lib/components/AboutMe.svelte";
    import Projects from "$lib/components/Projects.svelte";
	import Footer from "$lib/components/Footer.svelte";
</script>

<main>
    <HeroComponent/>
    <div class="bg-white rounded-3xl sm:p-15 md:p-10 lg:p-5 p-5 mb-10 shadow-2xl">
        <AboutMe/>
        <Projects/>
    </div>
    <Footer/>
</main>