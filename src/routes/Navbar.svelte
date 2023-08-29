<script lang="ts">
    import { page } from "$app/stores";
    import { Navbar, NavBrand, NavHamburger, NavUl, NavLi } from "flowbite-svelte";
    import logo from "$lib/images/svelte-logo.svg";
    $: activeUrl = $page.url.pathname;
</script>

<Navbar let:hidden let:toggle>
    <NavBrand href="/">
        <img src={logo} class="mr-3 h-6 sm:h-9" alt="logo" />
        <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">c sammen</span>
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <NavUl {activeUrl} {hidden}>
        <NavLi href="/">Home</NavLi>
        <NavLi href="/about">About</NavLi>
    </NavUl>
</Navbar>
