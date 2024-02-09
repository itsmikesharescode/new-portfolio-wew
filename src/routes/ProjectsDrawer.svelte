<script lang="ts">
    import * as Sheet from "$lib/components/ui/sheet";
    import { Button } from "$lib/components/ui/button";
    import { Input } from "$lib/components/ui/input";
    import { Label } from "$lib/components/ui/label";
    import * as Tooltip from "$lib/components/ui/tooltip";
    import { Folder } from 'lucide-svelte';
    import * as Card from "$lib/components/ui/card";
    import { ArrowUpRightSquare } from 'lucide-svelte';
    import {projectDynamicData} from "$lib";
</script>

<Sheet.Root>
    <Sheet.Trigger asChild let:builder class="">

        <Button builders={[builder]}  class="flex gap-1 items-center max-w-fit mx-auto lg:mx-0">
            <Folder size="20px"/>
            Created Projects
        </Button>
    </Sheet.Trigger>

    <Sheet.Content side="bottom" class="border-slate-600 " >
        <Sheet.Header>
            <Sheet.Title>Created Projects</Sheet.Title>
            <Sheet.Description>
                List of My Web Development Projects
            </Sheet.Description>
        </Sheet.Header>

        <div class="mt-5 flex flex-col gap-2 max-h-[75dvh] overflow-x-hidden overflow-y-auto sm:px-2">
            {#each $projectDynamicData as project }
                <Card.Root class="border-slate-600 border-0">

                    <Card.Header>
                        <Card.Title class="text-red-700">{project.project_title}</Card.Title>
                        <Card.Description>{project.description}</Card.Description>
                    </Card.Header>

                    <Card.Content class="flex flex-col  gap-4">
                        <div class="">
                            <iframe class="w-full md:h-[450px]" src={project.youtube_link} title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
                        </div>

                        <div class="flex flex-col gap-4 md:flex-row sm:gap-10">

                            <div class="flex flex-col gap-4 sm:border-l-2 sm:p-4">
                                <p class="font-medium">System Features:</p>
    
                                {#each project.system_features as feature }
                                    <div class="flex gap-2 ">
                                        <span class="flex h-2 w-2 translate-y-1 rounded-full bg-sky-500" />
                                        <div class="space-y-1">
                                            <p class="text-sm leading-none">{feature}</p>
                                        </div>
                                    </div>
                                {/each}
                                
                            </div>
    
                            <div class="flex flex-col gap-4 sm:border-l-2 sm:p-4">
                                <p class="font-medium">Technology Used:</p>
    
                                
                                <div class="flex gap-2 ">
                                    <span class="flex h-2 w-2 translate-y-1 rounded-full bg-sky-500" />
                                        <div class="space-y-1">
                                        <p class="text-sm leading-none">
                                            SvelteKit 
                                        </p>
                                    
                                    </div>
                                </div>
                                
                                <div class="flex gap-2 ">
                                    <span class="flex h-2 w-2 translate-y-1 rounded-full bg-sky-500" />
                                        <div class="space-y-1">
                                        <p class="text-sm leading-none">
                                            TailwindCSS 
                                        </p>
                                    
                                    </div>
                                </div>
    
                                <div class="flex gap-2 ">
                                    <span class="flex h-2 w-2 translate-y-1 rounded-full bg-sky-500" />
                                        <div class="space-y-1">
                                        <p class="text-sm leading-none">
                                            Supabase
                                        </p>
                                    
                                    </div>
                                </div>
                                
                                
                            </div>

                            <div class="flex flex-col gap-4 justify-start items-start sm:border-l-2 sm:p-4">
                                <p class="font-medium">Resource Link:</p>
                            
                                <div class="flex flex-col gap-2 ">
                                    {#each project.resource_link as link }
                                        <a href={link.link} target="_blank" class="text-sm flex gap-1 items-center transition-all hover:underline ">
                                            {link.link_title}<ArrowUpRightSquare size="15px" />
                                        </a>
                                       
                                    {/each}
                                </div>
                            </div>
                        </div>
                        
                    </Card.Content>

                  
                        
                       
                    

                </Card.Root>
            {/each}
        </div>
        

        <!-- <Sheet.Footer>
            <Sheet.Close asChild let:builder>
                <Button builders={[builder]} type="submit">Save changes</Button>
            </Sheet.Close>
        </Sheet.Footer> -->

    </Sheet.Content>

</Sheet.Root>
    
