<script lang="ts">
	import { goto } from "$app/navigation";
	import Button from "$lib/components/ui/button/button.svelte";
    import { Folder } from 'lucide-svelte';
    import { Linkedin } from 'lucide-svelte';
    import { Github } from 'lucide-svelte';
    import { Facebook } from 'lucide-svelte';
    import { Youtube } from 'lucide-svelte';
    import { BookOpenCheck } from 'lucide-svelte';
    import * as Tooltip from "$lib/components/ui/tooltip";
    import * as Avatar from "$lib/components/ui/avatar";
    import profile from "$lib/photos/profile.jpg";
	import ProjectsDrawer from "./ProjectsDrawer.svelte";


</script>

<div class="flex flex-col gap-4 min-h-screen mt-[10dvh] sm:mt-0 justify-center sm:max-w-[80%] mx-auto">

    
    <div class="flex flex-col gap-2 items-center">
        <h2 class="mt-10 text-center scroll-m-20 border-b pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0">
            Hi there, I'm <b class="bg-black text-white px-2 rounded-lg dark:bg-white dark:text-black">Mike John</b> a <b class="bg-black text-white px-2 rounded-lg dark:bg-white dark:text-black">Junior Web Developer</b>
        </h2>
        
        
        <blockquote class="mt-6 border-l-2 pl-6 italic flex flex-col gap-2 sm:flex-row items-center">
            <div class="">
                <Avatar.Root>
                    <Avatar.Image src={profile} alt="@mikejohn" />
                    <Avatar.Fallback>MJ</Avatar.Fallback>
                </Avatar.Root>
            </div>

            "As a passionate and curious individual, I have always been fascinated by the logic behind computers. This interest has led me to develop a strong foundation in web development, and I am constantly seeking to expand my knowledge and skills in this field. With my enthusiasm and dedication, I am confident that I can make a valuable contribution to any team."
        </blockquote>
    
        <blockquote class="mt-6 border-l-2 pl-6 italic flex flex-col gap-2 sm:flex-row items-center">
            <div class="">
                <Avatar.Root>
                    <Avatar.Image src={profile} alt="@mikejohn" />
                    <Avatar.Fallback>MJ</Avatar.Fallback>
                </Avatar.Root>
            </div>
            "I am confident that web development is a field with a bright future, and I am excited to be a part of it. In addition to my studies, I have also gained experience in making websites through my personal projects. I have built websites for my friends, family, and community organizations. I have also built websites for businesses and startups."
        </blockquote>

        <blockquote class="mt-6 border-l-2 pl-6 italic flex flex-col gap-2 sm:flex-row items-center">
            <div class="">
                <Avatar.Root>
                    <Avatar.Image src={profile} alt="@mikejohn" />
                    <Avatar.Fallback>MJ</Avatar.Fallback>
                </Avatar.Root>
            </div>
            <p>Focused on  <b class="text-red-600">SvelteKit</b>, <b class="text-red-600">TailwindCSS</b>, <b class="text-red-600"> Supabase</b>, and <b class="text-red-600">Firebase9</b>, I excel in crafting efficient and visually appealing web applications. Bonus proficiency in <b class="text-red-600">ReactJS</b> and <b class="text-red-600">Go lang</b> enhances my versatility in development.</p>
        </blockquote>
    </div>

    <div class="flex flex-col gap-4 lg:flex-row lg:items-center mt-5">

        <ProjectsDrawer />
        
        <Tooltip.Root>

            <Tooltip.Trigger asChild let:builder>
                <Button builders={[builder]}  variant="link" class="flex gap-1 items-center"
                on:click={() => window.open("https://www.linkedin.com/in/mike-john-eviota-4443a6288/")}
                >
                    <Linkedin size="20px"/>
                    LinkedIn
                </Button>
            </Tooltip.Trigger>
            
            <Tooltip.Content class="bg-black text-white dark:bg-white dark:text-black">
                <p>
                    Let's connect on LinkedIn! See what I'm up to by clicking here.
                </p>
            </Tooltip.Content>
        </Tooltip.Root>


        <Tooltip.Root>

            <Tooltip.Trigger asChild let:builder>
                <Button builders={[builder]}  variant="link" class="flex gap-1 items-center"
                on:click={() => window.open("https://github.com/itsmikesharescode")}
                >
                    <Github size="20px"/>
                    Github 
                </Button>
            </Tooltip.Trigger>
            
            <Tooltip.Content class="bg-black text-white dark:bg-white dark:text-black">
                <p>
                    I'm excited to share my latest work on Github. Check it out by clicking here.
                </p>
            </Tooltip.Content>
        </Tooltip.Root>

        <Tooltip.Root>

            <Tooltip.Trigger asChild let:builder>
                <Button builders={[builder]}  variant="link" class="flex gap-1 items-center"
                on:click={() => window.open("https://www.facebook.com/mike.eviota/")}
                >
                    <Facebook size="20px"/>
                    Facebook
                </Button>
            </Tooltip.Trigger>
            
            <Tooltip.Content class="bg-black text-white dark:bg-white dark:text-black">
                <p>
                    Let's connect on Facebook! See what I'm up to by clicking here.
                </p>
            </Tooltip.Content>
        </Tooltip.Root>

        <Tooltip.Root>

            <Tooltip.Trigger asChild let:builder>
                <Button builders={[builder]}  variant="link" class="flex gap-1 items-center"
                on:click={() => window.open("https://www.youtube.com/@mikeSharesCode")}
                >
                    <Youtube size="20px"/>
                    Youtube
                </Button>
            </Tooltip.Trigger>
            
            <Tooltip.Content class="bg-black text-white dark:bg-white dark:text-black">
                <p>
                    I'm excited to share my latest work on Youtube. Check it out by clicking here.
                </p>
            </Tooltip.Content>
        </Tooltip.Root>


        <Tooltip.Root>

            <Tooltip.Trigger asChild let:builder>
                <Button builders={[builder]}  variant="link" class="flex gap-1 items-center"
                on:click={() => window.open("https://docs.google.com/document/d/1JmVh6dJRAAEfLPQwJ89TIjd-_gvfdscO/edit?usp=drive_link&amp;ouid=109818094393525011989&amp;rtpof=true&amp;sd=true")}
                >
                    <BookOpenCheck size="20px"/>
                    View My CV
                </Button>
            </Tooltip.Trigger>
            
            <Tooltip.Content class="bg-black text-white dark:bg-white dark:text-black">
                <p>
                    View or download my CV/Resume by clicking here.
                </p>
            </Tooltip.Content>
        </Tooltip.Root>
    </div>
</div>