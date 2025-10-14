<script lang="ts">
    import heroImage from "$lib/assets/images/hero-image.png";
    import { Motion } from 'svelte-motion'; 
</script>

<section class="hero-container flex flex-col items-center pb-20 gap-12 pt-10" id="home">
    <div class="hero-image flex justify-center">
        <div class="hero-image flex justify-center">
		<Motion
			initial={{ opacity: 0, scale: 0.95 }}
			animate={{ opacity: 1, scale: 1 }}
			transition={{ duration: 0.6, ease: [0.25, 0.1, 0.25, 1] }}
		>
			<img
				src={heroImage}
				alt="Rebecca Lager"
				class="w-100 h-100 border-pink-100 border-5 rounded-full shadow-lg mx-auto object-cover"
			/>
		</Motion>
	</div>
    </div>
    <div class="hero-heading pt-10 text-center md:text-left">
        <h1 class="text-4xl md:text-4xl font-bold leading-tight">Rebecca</h1>
        <h1 class="text-4xl md:text-4xl font-bold leading-tight">Rebecca</h1>
    </div>
    <div class="hero-text pt-5 text-center md:text-center">
        <h2 class="text-lg text-center md:text-center">fullstack developer with a passion for design</h2>
    </div>
</section>
