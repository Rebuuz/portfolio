<script lang="ts">
    import * as Carousel from "$lib/components/ui/carousel"; 
    import * as Card from "$lib/components/ui/card"; 
    import portfolio from "$lib/assets/images/project-portfolio.png";
    import comingsoon from "$lib/assets/images/comingsoon.png";
	import { Button } from "./ui/button";
</script>

<section class="projects-section px-8 sm:px-6 md:px-8 lg:px-16" id="projects">
    <div class="flex flex-col">
        <h2 class="text-center text-3xl text-rose-300 pb-4">projects</h2> 
        <p class="text-center text-[#333]">these are some of the projects i have made!</p>
    </div>

       <div class="flex justify-center">
        <Carousel.Root class="w-full max-w-6xl">
            <Carousel.Content class="flex gap-4 px-2 sm:px-4 md:px-8 lg:px-16 py-10">
                <Carousel.Item class="basis-full sm:basis-1/2 lg:basis-1/3">
                    <a target="_blank" href="https://github.com/Rebuuz/portfolio">
                        <Card.Root class="rounded-2xl shadow-md py-0 transition-transform duration-300 hover:scale-105 hover:shadow-lg cursor-pointer">
                            <Card.Header class="px-0">
                                <img src={portfolio} alt="portfolio screenshot" class="object-fill rounded-t-2xl"/>
                                <Card.Title class="px-6 pt-4">Portfolio</Card.Title>
                                <Card.Description class="px-6">Created with Svelte, Tailwind, ShadCn</Card.Description>
                            </Card.Header>
                            <Card.Content>
                                <p class="flex flex-row">This is my first portfolio, created in Svelte with ♡</p>
                            </Card.Content>
                            <Card.Footer class="px-3 sm:px-4 md:px-6 pb-4 sm:pb-6">
                                <a target="_blank" href="https://github.com/Rebuuz/portfolio"><Button class="text-[#333] hover:bg-secondary cursor-pointer">Read more <svg class="w-4 h-4 me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                                    <path fill-rule="evenodd" d="M10 .333A9.911 9.911 0 0 0 6.866 19.65c.5.092.678-.215.678-.477 0-.237-.01-1.017-.014-1.845-2.757.6-3.338-1.169-3.338-1.169a2.627 2.627 0 0 0-1.1-1.451c-.9-.615.07-.6.07-.6a2.084 2.084 0 0 1 1.518 1.021 2.11 2.11 0 0 0 2.884.823c.044-.503.268-.973.63-1.325-2.2-.25-4.516-1.1-4.516-4.9A3.832 3.832 0 0 1 4.7 7.068a3.56 3.56 0 0 1 .095-2.623s.832-.266 2.726 1.016a9.409 9.409 0 0 1 4.962 0c1.89-1.282 2.717-1.016 2.717-1.016.366.83.402 1.768.1 2.623a3.827 3.827 0 0 1 1.02 2.659c0 3.807-2.319 4.644-4.525 4.889a2.366 2.366 0 0 1 .673 1.834c0 1.326-.012 2.394-.012 2.72 0 .263.18.572.681.475A9.911 9.911 0 0 0 10 .333Z" clip-rule="evenodd"/>
                                    </svg>
                                </Button></a>
                            </Card.Footer>
                        </Card.Root>
                    </a>
                </Carousel.Item>

                <Carousel.Item class="basis-full sm:basis-1/2 lg:basis-1/3">
                    <Card.Root class="rounded-2xl shadow-md py-0 transition-transform duration-300 hover:scale-105 hover:shadow-lg">
                        <Card.Header class="px-0">
                            <img src={comingsoon} alt="portfolio screenshot" class="object-fill rounded-t-2xl"/>
                            <Card.Title class="px-6 pt-4">Coming Soon</Card.Title>
                            <Card.Description class="px-6">Oh no, much empty!</Card.Description>
                        </Card.Header>
                        <Card.Content>
                            <p>This project is either in making or a little bit of a filler :)</p>
                        </Card.Content>
                        <Card.Footer class="px-3 sm:px-4 md:px-6 pb-4 sm:pb-6">
                            <Button class="text-[#333] hover:bg-secondary cursor-pointer">Read more <svg class="w-4 h-4 me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                                <path fill-rule="evenodd" d="M10 .333A9.911 9.911 0 0 0 6.866 19.65c.5.092.678-.215.678-.477 0-.237-.01-1.017-.014-1.845-2.757.6-3.338-1.169-3.338-1.169a2.627 2.627 0 0 0-1.1-1.451c-.9-.615.07-.6.07-.6a2.084 2.084 0 0 1 1.518 1.021 2.11 2.11 0 0 0 2.884.823c.044-.503.268-.973.63-1.325-2.2-.25-4.516-1.1-4.516-4.9A3.832 3.832 0 0 1 4.7 7.068a3.56 3.56 0 0 1 .095-2.623s.832-.266 2.726 1.016a9.409 9.409 0 0 1 4.962 0c1.89-1.282 2.717-1.016 2.717-1.016.366.83.402 1.768.1 2.623a3.827 3.827 0 0 1 1.02 2.659c0 3.807-2.319 4.644-4.525 4.889a2.366 2.366 0 0 1 .673 1.834c0 1.326-.012 2.394-.012 2.72 0 .263.18.572.681.475A9.911 9.911 0 0 0 10 .333Z" clip-rule="evenodd"/>
                                </svg></Button>
                        </Card.Footer>
                    </Card.Root>
                </Carousel.Item>

                <Carousel.Item class="basis-full sm:basis-1/2 lg:basis-1/3">
                    <Card.Root class="rounded-2xl shadow-md py-0 transition-transform duration-300 hover:scale-105 hover:shadow-lg">
                        <Card.Header class="px-0">
                            <img src={comingsoon} alt="portfolio screenshot" class="object-fill rounded-t-2xl"/>
                            <Card.Title class="px-6 pt-4">Coming Soon</Card.Title>
                            <Card.Description class="px-6">Oh no, much empty!</Card.Description>
                        </Card.Header>
                        <Card.Content>
                            <p>This project is either in making or a little bit of a filler :)</p>
                        </Card.Content>
                        <Card.Footer class="px-3 sm:px-4 md:px-6 pb-4 sm:pb-6">
                            <Button class="text-[#333] hover:bg-secondary cursor-pointer">Read more <svg class="w-4 h-4 me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                                <path fill-rule="evenodd" d="M10 .333A9.911 9.911 0 0 0 6.866 19.65c.5.092.678-.215.678-.477 0-.237-.01-1.017-.014-1.845-2.757.6-3.338-1.169-3.338-1.169a2.627 2.627 0 0 0-1.1-1.451c-.9-.615.07-.6.07-.6a2.084 2.084 0 0 1 1.518 1.021 2.11 2.11 0 0 0 2.884.823c.044-.503.268-.973.63-1.325-2.2-.25-4.516-1.1-4.516-4.9A3.832 3.832 0 0 1 4.7 7.068a3.56 3.56 0 0 1 .095-2.623s.832-.266 2.726 1.016a9.409 9.409 0 0 1 4.962 0c1.89-1.282 2.717-1.016 2.717-1.016.366.83.402 1.768.1 2.623a3.827 3.827 0 0 1 1.02 2.659c0 3.807-2.319 4.644-4.525 4.889a2.366 2.366 0 0 1 .673 1.834c0 1.326-.012 2.394-.012 2.72 0 .263.18.572.681.475A9.911 9.911 0 0 0 10 .333Z" clip-rule="evenodd"/>
                                </svg></Button>
                        </Card.Footer>
                    </Card.Root>
                </Carousel.Item>

                <Carousel.Item class="basis-full sm:basis-1/2 lg:basis-1/3">
                    <Card.Root class="rounded-2xl shadow-md py-0 transition-transform duration-300 hover:scale-105 hover:shadow-lg">
                        <Card.Header class="px-0">
                            <img src={comingsoon} alt="portfolio screenshot" class="object-fill rounded-t-2xl"/>
                            <Card.Title class="px-6 pt-4">Portfolio</Card.Title>
                            <Card.Description class="px-6">Oh no, much empty!</Card.Description>
                        </Card.Header>
                        <Card.Content>
                            <p>This project is either in making or a little bit of a filler :)</p>
                        </Card.Content>
                        <Card.Footer class="px-3 sm:px-4 md:px-6 pb-4 sm:pb-6">
                            <Button class="text-[#333] hover:bg-secondary cursor-pointer">Read more <svg class="w-4 h-4 me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                                <path fill-rule="evenodd" d="M10 .333A9.911 9.911 0 0 0 6.866 19.65c.5.092.678-.215.678-.477 0-.237-.01-1.017-.014-1.845-2.757.6-3.338-1.169-3.338-1.169a2.627 2.627 0 0 0-1.1-1.451c-.9-.615.07-.6.07-.6a2.084 2.084 0 0 1 1.518 1.021 2.11 2.11 0 0 0 2.884.823c.044-.503.268-.973.63-1.325-2.2-.25-4.516-1.1-4.516-4.9A3.832 3.832 0 0 1 4.7 7.068a3.56 3.56 0 0 1 .095-2.623s.832-.266 2.726 1.016a9.409 9.409 0 0 1 4.962 0c1.89-1.282 2.717-1.016 2.717-1.016.366.83.402 1.768.1 2.623a3.827 3.827 0 0 1 1.02 2.659c0 3.807-2.319 4.644-4.525 4.889a2.366 2.366 0 0 1 .673 1.834c0 1.326-.012 2.394-.012 2.72 0 .263.18.572.681.475A9.911 9.911 0 0 0 10 .333Z" clip-rule="evenodd"/>
                                </svg></Button>
                        </Card.Footer>
                    </Card.Root>
                </Carousel.Item>
            </Carousel.Content>

            <div class="flex justify-center mt-6 gap-4">
                <Carousel.Previous class="rounded-full bg-rose-300 text-white hover:bg-rose-400 transition" />
                <Carousel.Next class="rounded-full bg-rose-300 text-white hover:bg-rose-400 transition" />
            </div>
        </Carousel.Root>
    </div>
</section>