<script>
    import "../app.css";
    import { Footer, FooterCopyright, FooterLink, FooterLinkGroup, Navbar, NavBrand, NavHamburger, NavUl, NavLi, FooterBrand } from 'flowbite-svelte';
    import { page } from '$app/stores';
</script>

<svelte:head>
    <meta name="description" content="Découvrez les saveurs authentiques de l'Italie au cœur d'Annoeullin, avec notre pizzeria et restaurant de pâtes. Des pizzas fraîches, des pâtes al dente et une sélection de boissons rafraîchissantes vous attendent chez nous.">

    <meta name="description" content="Situé dans le charmant Nord de la France, notre restaurant de restauration rapide à Annoeullin vous offre une expérience gastronomique italienne inoubliable. Des pizzas croustillantes, des pâtes savoureuses et des boissons pour tous les goûts vous attendent.">

    <meta name="description" content="Envie d'une pause gourmande à Annoeullin? Venez savourer nos délicieuses pizzas et nos pâtes fraîches dans notre restaurant de restauration rapide. Avec un large choix de boissons, vous trouverez sûrement de quoi étancher votre soif.">

    <meta name="description" content="Plongez dans l'ambiance chaleureuse de l'Italie à Annoeullin avec notre pizzeria et restaurant de pâtes. Des recettes traditionnelles préparées avec soin, des boissons fraîches et un accueil convivial vous attendent pour un repas délicieux et rapide.">

    <meta name="description" content="Bienvenue dans notre oasis italienne au cœur d'Annoeullin! Venez découvrir notre sélection de pizzas artisanales, de pâtes fraîches et de boissons désaltérantes. Un voyage gustatif rapide et délicieux vous attend dans notre restaurant de restauration rapide.">

    <meta property="og:title" content="Festi pizza - Pizzeria et restaurant de pâtes à Annoeullin">
    <meta property="og:description" content="Découvrez les saveurs authentiques de l'Italie au cœur d'Annoeullin, avec notre pizzeria et restaurant de pâtes. Des pizzas fraîches, des pâtes al dente et une sélection de boissons rafraîchissantes vous attendent chez nous.">
    <meta property="og:image" content="/favicon.jpg">
    <meta property="og:url" content="https://festipizza-site.vercel.app">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Festi pizza - Pizzeria et restaurant de pâtes à Annoeullin">
    <meta name="twitter:description" content="Découvrez les saveurs authentiques de l'Italie au cœur d'Annoeullin, avec notre pizzeria et restaurant de pâtes. Des pizzas fraîches, des pâtes al dente et une sélection de boissons rafraîchissantes vous attendent chez nous.">
    <meta name="twitter:image" content="/favicon.jpg">

</svelte:head>

{#if $page.error == null}
<Navbar color="green" >
    <NavBrand href="/">
        <img src="/favicon.jpg" class="me-3 h-6 sm:h-9" alt="Festi pizza Logo" />
        <title class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Festi pizza</title>
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
            <FooterBrand href="/" src="/favicon.jpg" alt="Festi pizza" name="Festi pizza" />
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