<script lang="ts">
    import HeroComponent from "$lib/components/Hero.svelte";
    import AboutMe from "$lib/components/AboutMe.svelte";
    import Projects from "$lib/components/Projects.svelte";
	import Footer from "$lib/components/Footer.svelte";
</script>

<main>
    <HeroComponent/>
    <div class="bg-white rounded-3xl md:p-20 p-5 mb-15 shadow-2xl">
        <AboutMe/>
        <Projects/>
    </div>
    <Footer/>
</main>