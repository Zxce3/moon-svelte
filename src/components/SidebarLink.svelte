<script>
    export let links = [];

    function isActive(link) {
        return link.active ? "active" : "";
    }
</script>

<ul class="sidebar-nav">
    {#each links as link, index (index)}
        {#if link.divider}
            <li key={index}>
                {link.name}
                <hr class="sidebar-divider" />
            </li>
        {:else}
            <li class="nav-item" key={index}>
                <a
                    class="nav-link {isActive(link)}"
                    href={link.url}
                    aria-current={link.active ? "page" : null}
                >
                    {link.name}
                </a>
            </li>
        {/if}
    {/each}
</ul>
