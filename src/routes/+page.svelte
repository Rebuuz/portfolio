<script lang="ts">
    import HeroComponent from "$lib/components/Hero.svelte";
    import AboutMe from "$lib/components/AboutMe.svelte";
    import Projects from "$lib/components/Projects.svelte";
	import Footer from "$lib/components/Footer.svelte";
</script>

<main>
    <HeroComponent/>
    <div class="projects-section bg-white rounded-3xl p-20 mb-5 shadow-2xl">
        <AboutMe/>
        <Projects/>
    </div>
    <Footer/>
</main>