<script lang="ts">
    import myPhoto from "$lib/assets/images/rebeccalager.png";
	import * as Accordion from "$lib/components/ui/accordion"; 
    import { CircleArrowLeft } from "lucide-svelte";
</script>


<section class="aboutme-section bg-white rounded-3xl p-20 mb-20 shadow-2xl" id="about-me">
    <div class="flex flex-row justify-between">
        <div class="aboutme-container grid grid-cols-2">
            <img alt="Rebecca Lager" src="{myPhoto}" class="mx-auto w-50 rounded-full shadow-2xl" />
            <div class="text-container">
                <CircleArrowLeft/>
                <h2 class="pt-10 text-left pb-5 text-2xl text-rose-300">about me</h2>
                <p class="text-left">Here is some information about myself in general</p>
            </div>
        </div>
       <Accordion.Root type="single" class="w-xl ml-10">
            <Accordion.Item value="item-1">
                <Accordion.Trigger>Skills</Accordion.Trigger>
                <Accordion.Content>
                    Yes. It adheres to the WAI-ARIA design pattern.
                </Accordion.Content>
            </Accordion.Item>

            <Accordion.Item value="item-2">
                <Accordion.Trigger>Another question?</Accordion.Trigger>
                <Accordion.Content>
                    Some more content here.
                </Accordion.Content>
            </Accordion.Item>
        </Accordion.Root>
    </div>
</section>
