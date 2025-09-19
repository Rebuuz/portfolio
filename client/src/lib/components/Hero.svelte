<script lang="ts">
    import heroImage from "$lib/assets/images/hero-image.png";
</script>

<section class=" hero-container flex flex-col items-center min-h-screen px-8 gap-12">
    <div class="hero-image flex justify-center">
        <img 
        src={heroImage} 
        alt="Rebecca Lager"
        class="w-100 h-100 border-pink-100 border-5 p-8 rounded-full shadow-lg mx-auto object-cover"
        />
    </div>
    <div class="hero-heading text-center md:text-left">
        <h1 class="text-4xl md:text-4xl font-bold leading-tight">Rebecca</h1>
        <h1 class="text-4xl md:text-4xl font-bold leading-tight">Rebecca</h1>
    </div>
    <div class="hero-text text-center md:text-center">
        <p class="text-lg text-center md:text-center">fullstack developer with a passion for design</p>
    </div>
</section>

<style>
.hero-container {
    padding-top: 5rem;
}

.hero-heading {
    padding-top: 4rem;
    font-family: 'Poppins', sans-serif;
    position: relative;
}

.hero-heading h1 {
    color: #b8c995;
    font-size: 8em;
    position: absolute;
    transform: translate(-50%, -50%);
}

.hero-heading h1:nth-child(1) {
    color: transparent;
    -webkit-text-stroke: 2px #b8c995;
}

.hero-heading h1:nth-child(2) {
    color: #65704f;
    animation: animate 4s ease-in-out infinite;
}

@keyframes animate {
	0%,
	100% {
		clip-path: polygon(
			0% 45%,
			16% 44%,
			33% 50%,
			54% 60%,
			70% 61%,
			84% 59%,
			100% 52%,
			100% 100%,
			0% 100%
		);
	}

	50% {
		clip-path: polygon(
			0% 60%,
			15% 65%,
			34% 66%,
			51% 62%,
			67% 50%,
			84% 45%,
			100% 46%,
			100% 100%,
			0% 100%
		);
	}
}

.hero-text {
    padding-top: 1rem;
    font-family: 'Poppins', sans-serif;
    
}
</style>