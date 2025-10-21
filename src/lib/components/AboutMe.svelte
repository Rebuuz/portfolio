<script lang="ts">
    import myPhoto from "$lib/assets/images/rebeccalager.png";
	import * as Accordion from "$lib/components/ui/accordion"; 
    import { CircleArrowLeft, CircleArrowUp, Asterisk, School, FileDown, BadgeCheck, X, BadgeX } from "lucide-svelte";
	import Button from "./ui/button/button.svelte";
    import { fly } from "svelte/transition";
    import { tick } from "svelte";
    import emailjs from "@emailjs/browser";

    //popups
    let showToast = false;
    let showContact = false;
    let emailSent: boolean | null = null; //if null - not sent, if true = sent, false = failed to send

    //contact popup information
    let name = "";
    let email = "";
    let message = "";

    //error 
    let nameError = "";
    let emailError = "";
    let messageError = "";

    //download cv function
  async function handleDownload() {
    showToast = true;
    await tick();

    setTimeout(() => {
      showToast = false;
    }, 3000);
  }

  //email validation function
  function validateEmail(email:string) {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/; 
    return re.test(email);
  }
  
  //sending email function
  async function sendEmail() {
    nameError = "";
    emailError = "";
    messageError = "";

    let hasError = false;

    if (!name) {
        nameError = "Please enter a name";
        hasError = true;
    } 

    if (!email) {
        emailError = "Please enter an email address";
        hasError = true;
    } 

    if (!message) {
        messageError = "Please enter a message";
        hasError = true;
    } 

    if (!validateEmail(email)) {
        emailError = "Please enter a valid email adress"
        hasError = true;
    }

    if(hasError) return; //stop if there is an error

    //send email with emailjs
    try {
        await emailjs.send(
            "service_g37q6j6",
            "template_v4pb1fd",
            {
                from_name: name,
                from_email: email,
                message: message
            },
            "4-4eSBBfV5lmz6Sg0"
        );
        emailSent = true;

        //closing the popup after email has been sent 
        setTimeout(() => {
            showContact = false;
            emailSent = null;
            name = "";
            email = "";
            message = "";
        }, 2000);
    } catch (error) {
        console.error("Email failed to send", error);
        emailSent = false;
    }
  }
</script>

<section class="aboutme-section mb-20 mt-10 px-4 md:px-8 lg:px-16" id="about-me">
    <div class="flex flex-col lg:flex-row items-center lg:items-start gap-10 justify-between">
        <div class="flex flex-col sm:flex-row gap-6 col-span-2 items-center sm:items-start">
            <img alt="Rebecca Lager" src="{myPhoto}" class="mx-auto w-40 h-60 sm:w-45 lg:h-64 object-cover rounded-full shadow-2xl border-4 border-primary" />
            <div class="text-container text-center sm:text-left">
                <div class="flex flex-row items-center justify-center sm:justify-start gap-2 pt-3">
                    <div class="icon text-primary block sm:hidden">
                        <CircleArrowUp/>
                    </div>
                    <div class="icon text-primary hidden sm:block">
                        <CircleArrowLeft/>
                    </div>
                    <h2 class="text-3xl text-rose-300">about me</h2>
                </div>
                <p class="text-base pt-4 leading-relaxed max-w-prose">I'm Rebecca Lager, a junior fullstack developer with a strong interest in frontend development. I enjoy creating clean, user-friendly interfaces and am always curious to learn new technologies that improve the user experience. In my spare time, I play games, cuddle with my cats, hang out with my family, knit and so on!</p>
                <Button class="text-[#333] hover:bg-secondary cursor-pointer mt-4" onclick={() => showContact = true}>
                    Contact me!
                </Button>

                {#if showContact}
                    <!-- Overlay -->
                    <div 
                        class="fixed inset-0 bg-transparent z-40"
                        onclick={() => showContact = false}
                        role="button"
                        tabindex="0"
                        onkeydown={(e) => e.key === 'Enter' && (showContact = false)}
                    ></div>

                    <!-- Popup -->
                    <div 
                        class="fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-50 px-8 py-5 border-2 border-primary bg-white rounded-2xl shadow-2xl flex flex-col gap-4 w-100"
                        transition:fly={{ y: 20, duration: 300 }}
                        onclick={(e) => e.stopPropagation()}
                        role="button"
                        tabindex="0"
                        onkeydown={(e) => e.key === 'Enter' && e.stopPropagation()}
                        >

                        <!-- Krysset -->
                        <X 
                            class="absolute top-4 right-4 cursor-pointer text-[333]" 
                            onclick={() => showContact = false}
                        />
                        <h2 class="text-rose-300 text-center">Contact me</h2>

                        {#if emailSent === true}
                        <div class="flex flex-col items-center gap-4 text-center">
                            <BadgeCheck class="text-primary w-32 h-32"/>
                            <span class="text-primary text-xl">Message sent successfully!</span>
                        </div>
                        {:else if emailSent === false}
                        <div class="flex flex-col items-center gap-4 text-center">
                            <BadgeX class="text-primary w-32 h-32"/>
                            <span class="text-red-400 text-xl">Failed to send message. Try again!</span>
                        </div>
                        {:else}
                            <input 
                                type="text" 
                                placeholder="Your name" 
                                bind:value={name} 
                                class="border p-2 rounded-xl w-full focus:border-primary focus:border-2 focus:outline-none {nameError ? 'border-red-400' : 'border'} focus:ring-0"
                                oninput={() => nameError = ""}/>
                            {#if nameError}
                                <span class="text-red-400 text-sm">{nameError}</span>
                            {/if}
                            <input 
                                type="email" 
                                placeholder="Your email" 
                                bind:value={email}
                                class="border p-2 rounded-xl w-full focus:border-primary focus:border-2 focus:outline-none {emailError ? 'border-red-400' : 'border'} focus:ring-0" 
                                oninput={() => emailError = ""}/>
                            {#if emailError}
                                <span class="text-red-400 text-sm">{emailError}</span>
                            {/if}
                            <textarea 
                                placeholder="Your message" bind:value={message} 
                                class="border p-2 rounded-xl w-full focus:border-primary focus:border-2 focus:outline-none {messageError ? 'border-red-400' : 'border'} focus:ring-0"
                                oninput={() => messageError = ""}></textarea>
                            {#if messageError}
                                <span class="text-red-400 text-sm">{messageError}</span>
                            {/if}
                            <Button class="text-[#333] hover:bg-secondary cursor-pointer mt-4" onclick={sendEmail}>Send</Button>
                        {/if}
                    </div>
                {/if}
            </div>
        </div>

        <Accordion.Root type="single" class="w-full lg:w-1/3">
            <Accordion.Item value="item-1" class="mb-2 border-primary border-2 rounded-xl bg-primary shadow-sm">
            <Accordion.Trigger class="px-5 text-xl hover:no-underline flex w-full items-center justify-between text-left">skills</Accordion.Trigger>
            <Accordion.Content class="px-5 rounded-b-xl pt-4 mt-2 text-sm bg-white">
                <p class="pb-5">Trying out new skills is always fun, but this is a list of some of the skills I have.</p>
                {#each ['.NET/C#', 'Javascript', 'HTML/CSS (Tailwind)', 'React', 'Umbraco', 'Svelte'] as skills}
                <p class=" flex flex-row items-center gap-2">
                    <Asterisk class="text-secondary" /> {skills}
                </p>
                {/each}
            </Accordion.Content>
            </Accordion.Item>

            <Accordion.Item value="item-2" class="mb-2 border-primary border-2 rounded-xl bg-primary shadow-sm">
            <Accordion.Trigger class="px-5 text-bolder text-xl hover:no-underline flex w-full items-center justify-between text-left">education</Accordion.Trigger>
            <Accordion.Content class="px-5 rounded-b-xl pt-4 mt-2 text-sm bg-white">
                <p class=" flex flex-row items-center gap-2 pb-2">
                    <School class="text-secondary" /> EC Utbildning (2023-2025)
                </p>
                <p class=" flex flex-row items-center gap-2 pb-2">
                    <School class="text-secondary" /> Webmaster (2020-2022) 
                </p>
            </Accordion.Content>
            </Accordion.Item>

            <Accordion.Item value="item-3" class="mb-2 border-primary border-2 rounded-xl bg-primary shadow-sm">
            <Accordion.Trigger class="px-5 text-bolder text-xl hover:no-underline flex w-full items-center justify-between text-left">cv</Accordion.Trigger>
            <Accordion.Content class="px-5 rounded-b-xl pt-4 mt-2 text-sm bg-white mb-0.5">
                <p class="pb-5">Want to read a little bit more? Download my CV down below to get more information:</p>
                <Button class="text-[#333] hover:bg-secondary cursor-pointer">
                    <a href="portfolio/CV__RebeccaLager_English.pdf" download="Rebecca-Lager-CV.pdf" onclick={handleDownload} class="flex flex-row items-center">
                        <FileDown class="mr-2" /> download (pdf)
                    </a>
                </Button>

                {#if showToast}
                    <div 
                        class="fixed inset-0 flex items-center justify-center px-6"
                        transition:fly={{ y: 20, duration: 300 }}>
                        <div class="bg-white border-2 border-primary rounded-2xl shadow-2xl p-6 flex flex-col items-center gap-4 text-center">
                            <BadgeCheck class="text-primary w-32 h-32"/>
                            <span class="text-[#333] text-2xl">CV downloaded successfully!</span>
                        </div>
                </div>
                {/if}
            </Accordion.Content>
            </Accordion.Item>
        </Accordion.Root>
    </div>
</section>
