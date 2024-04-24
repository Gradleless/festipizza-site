<script>
    import "../app.css";
    import { Footer, FooterCopyright, FooterLink, FooterLinkGroup, Navbar, NavBrand, NavHamburger, NavUl, NavLi, FooterBrand } from 'flowbite-svelte';
    import { page } from '$app/stores';
</script>

<svelte:head>
    <meta name="description" content="Découvrez les saveurs authentiques à d'Annoeullin, avec notre pizzeria et restaurant de pâtes. Des pizzas fraîches, des pâtes et une sélection de boissons.">

    <meta property="og:title" content="Festi pizza - Pizzeria et restaurant de pâtes à Annoeullin">
    <meta property="og:description" content="Découvrez les saveurs authentiques de l'Italie au cœur d'Annoeullin, avec notre pizzeria et restaurant de pâtes. Des pizzas fraîches, des pâtes al dente et une sélection de boissons rafraîchissantes vous attendent chez nous.">
    <meta property="og:image" content="/favicon.webp">
    <meta property="og:url" content="https://festipizza-site.vercel.app">

    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Festi pizza - Pizzeria et restaurant de pâtes à Annoeullin">
    <meta name="twitter:description" content="Découvrez les saveurs authentiques de l'Italie au cœur d'Annoeullin, avec notre pizzeria et restaurant de pâtes. Des pizzas fraîches, des pâtes al dente et une sélection de boissons rafraîchissantes vous attendent chez nous.">
    <meta name="twitter:image" content="/favicon.webp">

    <!-- Les keywords ne sont plus vraiment utiles de nos jours, mais ça ne coûte rien de les mettre quand même... -->
    <meta name="keywords" content="pizza, pizzeria, restaurant, pâtes, Annoeullin, saveurs, Italie, rapide">
    <meta name="robots" content="index, follow">
    <link rel="canonical" href="https://festipizza-site.vercel.app">
</svelte:head>

{#if $page.error == null}
<Navbar color="green" >
    <NavBrand href="/">
        <img src="/favicon.webp" class="me-3 h-6 sm:h-9" alt="Festi pizza Logo" />
        <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Festi pizza</span>
    </NavBrand>
    <NavHamburger  />
    <NavUl nonActiveClass="text-gray-700 hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-green-700 dark:text-gray-400 md:dark:hover:text-green-400 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
        <NavLi href="/">Accueil</NavLi>
        <NavLi href="/carte">Carte</NavLi>
        <NavLi href="/contact">Contact</NavLi>
    </NavUl>
</Navbar>
{/if}

<main class="min-h-screen">
    <slot></slot>
</main>

{#if $page.error == null}
<div class="mt-12">
    <Footer footerType="logo">
        <div class="sm:flex sm:items-center sm:justify-between">
            <FooterBrand href="/" src="/favicon.webp" alt="Festi pizza" name="Festi pizza" />
            <FooterLinkGroup ulClass="flex flex-wrap items-center mb-6 text-sm text-gray-500 sm:mb-0 dark:text-gray-400">
                <FooterLink href="/" liClass="me-4 last:me-0 md:me-6 transition ease-in dark:hover:text-green-700" aClass="no-underline">Accueil</FooterLink>
                <FooterLink href="/carte" liClass="me-4 last:me-0 md:me-6 transition ease-in dark:hover:text-green-700" aClass="no-underline">Carte</FooterLink> 
                <FooterLink href="/contact" liClass="me-4 last:me-0 md:me-6 transition ease-in dark:hover:text-green-700" aClass="no-underline">Contact</FooterLink>
                <FooterLink href="https://lycia.anhost.fr" liClass="me-4 last:me-0 md:me-6 transition ease-in dark:hover:text-green-700" aClass="no-underline">A propos</FooterLink>
            </FooterLinkGroup>
        </div>
        <hr class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8" />
        <FooterCopyright href="/" by="Festi pizza -" class="dark:hover:no-underline" aClass="no-underline"/>
    </Footer>
</div>
{/if}