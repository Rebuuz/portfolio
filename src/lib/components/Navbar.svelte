<script lang="ts">
    import { slide } from 'svelte/transition';
    import { onMount } from 'svelte';
    let isOpen = false;
    let activeSection = 'home';
    let ignoreScroll = false;

    const sections = ['home', 'about-me', 'projects'];

   function handleClick(section: string) {
    activeSection = section;
    isOpen = false;
    ignoreScroll = true;

    const el = document.getElementById(section);
    const navbar = document.querySelector('.navbar-section') as HTMLElement | null;
    const navbarHeight = navbar?.offsetHeight || 80;

    if (el) {
      window.scrollTo({
        top: el.offsetTop - navbarHeight + 5,
        behavior: 'smooth'
      });
    }

    setTimeout(() => {
      ignoreScroll = false;
    }, 600);
  }

  // 🟡 onMount kommer efteråt
  onMount(() => {
    function handleScroll() {
      if (ignoreScroll) return;

      const navbar = document.querySelector('.navbar-section') as HTMLElement | null;
      const navbarHeight = navbar?.offsetHeight || 80;
      const scrollPos = window.scrollY + navbarHeight + window.innerHeight / 4;

      let currentSection = sections[0];

      for (const id of sections) {
        const el = document.getElementById(id);
        if (el) {
          const top = el.offsetTop;
          const bottom = top + el.offsetHeight;
          if (scrollPos >= top && scrollPos < bottom) {
            currentSection = id;
            break;
          }
        }
      }

      activeSection = currentSection;
    }

    window.addEventListener('scroll', handleScroll);
    handleScroll();

    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
</script>

<header class="navbar-section sticky top-0 z-50 mx-auto 
        w-full sm:w-[100%] lg:w-[100%]
        rounded-b-2xl lg:rounded-b-2xl
        bg-white/80 border-none shadow-xl
        p-4">
    <div class="navbar-items mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-start md:justify-center gap-10 items-center">
            <!--desktop menu-->
            <div class="hidden md:flex space-x-8">
                {#each sections as section}
                    <a href={'#' + section}
                        on:click={() => handleClick(section)}
                        class="hover-underline hover:text-secondary transition cursor-pointer"
                        class:text-secondary={activeSection === section}
                        class:active-underline={activeSection === section}>
                        {section.replace('-', ' ')}
                    </a>
                {/each}
            </div>

            <!--mobile menu-->
            <button class="md:hidden focus:outline-none" aria-expanded={isOpen} on:click={() => (isOpen = !isOpen)}>
                {#if isOpen}
                ✖
                {:else}
                ☰
                {/if}
            </button>
        </div>
    </div>
    <!--mobile menu items-->
    {#if isOpen}
        <div
          class="md:hidden bg-transparent px-4 pb-4 space-y-2 pt-4" in:slide={{ duration: 450 }} out:slide={{ duration: 400 }}>
            {#each sections as section}
                        <a href={'#' + section}
                          class="block hover:text-secondary transition"
                          class:text-secondary={activeSection === section}
                          class:underline={activeSection === section}>
                          {section.replace('-', ' ')}
                        </a>
                    {/each}
        </div>
    {/if}
</header>
