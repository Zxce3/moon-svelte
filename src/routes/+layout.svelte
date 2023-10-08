<script>
    import "halfmoon/css/halfmoon.min.css";
    import "halfmoon/css/cores/halfmoon.cores.css";
    import Nav from "../components/Nav.svelte";
    import "bootstrap-icons/font/bootstrap-icons.css";
    import Loading from "../components/Loading.svelte";
    import { onMount, afterUpdate } from "svelte";
    let loading = true;

    afterUpdate(() => {
        setTimeout(() => {
            loading = false;
        }, 3000);
    });
    onMount(() => {
        const script = document.createElement("script");
        script.src =
            "https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js";
        script.integrity =
            "sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL";
        script.crossOrigin = "anonymous";
        document.body.appendChild(script);
    });
</script>

{#if loading}
    <Loading text="Loading... Please wait" />
{:else}
    <Nav />
    <div class="container">
        <slot />
    </div>
{/if}
