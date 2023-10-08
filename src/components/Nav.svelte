<script>
    import ThemeSwitcher from "./ThemeSwitcher.svelte";
    import CoreSwitcher from "./CoreSwitcher.svelte";
    import SidebarLink from "./SidebarLink.svelte";

    let links = [
        { name: "Getting started", divider: true },
        { name: "About", url: "about", active: true },
        { name: "CLI commands", url: "#" },
        { name: "Components", divider: true },
        { name: "File explorer", url: "#" },
        { name: "Spreadsheet", url: "#" },
        { name: "Maps", url: "#" },
        { name: "Messenger", url: "#" },
    ];
</script>

<nav
    class="navbar"
    style="background-color: var(--bs-content-bg); border-bottom: var(--bs-border-width) solid var(--bs-content-border-color);"
>
    <div class="container-fluid flex-nowrap">
        <div
            class="btn-group d-md-none"
            role="group"
            aria-label="Basic example"
        >
            <button
                type="button"
                data-bs-toggle="offcanvas"
                data-bs-target="#sidebar-example"
                class="btn btn-secondary"
            >
                <i class="bi bi-layout-sidebar" />
            </button>
            <ThemeSwitcher />
        </div>
        <a class="navbar-brand" href="/">
            <img src="favicon.png" alt="Logo" width="24" height="24" />
        </a>
        <CoreSwitcher />
    </div>
</nav>
<nav
    class="sidebar offcanvas-start offcanvas-md"
    tabindex="-1"
    id="sidebar-example"
>
    <div
        class="offcanvas-header border-bottom border-secondary border-opacity-25"
    >
        <a class="sidebar-brand font-weight-bolder" href="/"> SvelteKit </a>
        <span class="d-none d-md-inline-block">
            <ThemeSwitcher />
        </span>
        <button
            type="button"
            class="btn-close d-md-none"
            data-bs-dismiss="offcanvas"
            aria-label="Close"
            data-bs-target="#sidebar-example"
        />
    </div>
    <div class="offcanvas-body">
        <div class="mt-2 mb-3">
            <input type="text" class="form-control" placeholder="Search" />
        </div>
        <SidebarLink {links} />
    </div>
</nav>
