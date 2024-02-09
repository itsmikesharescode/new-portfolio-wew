<script lang="ts">
    import DarkMode from "$lib/my-components/DarkMode.svelte";
    import "../app.pcss";
    import { ModeWatcher } from "mode-watcher";
</script>
<ModeWatcher />

<div class="fixed m-2 right-0">
    <DarkMode />
</div>

<div class="p-4">
    <slot/>
</div>