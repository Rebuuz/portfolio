<script lang="ts">
    import HeroComponent from "$lib/components/Hero.svelte";
    import AboutMe from "$lib/components/AboutMe.svelte";
    import Projects from "$lib/components/Projects.svelte";
	import { DivideSquareIcon } from "lucide-svelte";
</script>

<main>
    <HeroComponent></HeroComponent>
    <div class="projects-section bg-white rounded-3xl p-20 mb-20 shadow-2xl">
        <AboutMe></AboutMe>
        <Projects></Projects>
    </div>
</main>