<script lang="ts">
    import myPhoto from "$lib/assets/images/rebeccalager.png";
	import * as Accordion from "$lib/components/ui/accordion"; 
    import { CircleArrowLeft, Asterisk } from "lucide-svelte";
</script>


<section class="aboutme-section bg-white rounded-3xl p-20 mb-20 shadow-2xl" id="about-me">
    <div class="flex flex-row justify-between">
        <div class="flex flex-row gap-6 col-span-2">
            <img alt="Rebecca Lager" src="{myPhoto}" class="mx-auto w-64 h-64 object-cover rounded-full shadow-2xl border-4 border-primary" />
            <div class="text-container">
                <div class="flex flex-row items-center gap-2 pt-3">
                    <div class="icon text-primary">
                        <CircleArrowLeft/>
                    </div>
                    <div class="about-me-title">
                        <h2 class="text-left text-2xl text-rose-300">about me</h2>
                    </div>
                </div>
            <p class="text-left pt-4">I'm Rebecca Lager, a junior fullstack developer with a strong interest in frontend development. I enjoy creating clean, user-friendly interfaces and am always curious to learn new technologies that improve the user experience.</p>
            </div>
        </div>

        <Accordion.Root type="single" class="w-12/12 ml-10">
            <Accordion.Item value="item-1" class="mb-2 border-primary border-2 rounded-xl bg-primary shadow-sm">
            <Accordion.Trigger class="px-5 text-bolder text-xl hover:no-underline flex w-full items-center justify-between text-left">skills</Accordion.Trigger>
            <Accordion.Content class="px-5 transition-all duration-800 ease-in-out rounded-b-xl pt-4 mt-2 text-sm bg-white text-text-color">
                <p class="pb-5">Trying out new skills is always fun, but this is a list of some of the skills I have.</p>
                <p class=" flex flex-row items-center">
                    <Asterisk class="text-secondary" /> .NET/C#
                </p>
                <p class="flex flex-row items-center">
                    <Asterisk class="text-secondary" /> Javascript
                </p>
                <p class="flex flex-row items-center">
                    <Asterisk class="text-secondary" /> HTML/CSS
                </p>
                <p class="flex flex-row items-center">
                    <Asterisk class="text-secondary" /> React
                </p>
                <p class="flex flex-row items-center">
                    <Asterisk class="text-secondary" /> Umbraco
                </p>
                <p class="flex flex-row items-center">
                    <Asterisk class="text-secondary" /> Tailwind
                </p>
                <p class="flex flex-row items-center">
                    <Asterisk class="text-secondary" /> Svelte
                </p>
            </Accordion.Content>
            </Accordion.Item>

            <Accordion.Item value="item-2">
            <Accordion.Trigger class="px-5 text-bolder text-xl hover:no-underline bg-primary rounded-full">education</Accordion.Trigger>
            <Accordion.Content>
                Some more content here.
            </Accordion.Content>
            </Accordion.Item>
        </Accordion.Root>
    </div>
</section>
