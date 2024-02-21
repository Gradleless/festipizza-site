<script>
    import "../app.css";
    import { Footer, FooterCopyright, FooterLink, FooterLinkGroup, Navbar, NavBrand, NavHamburger, NavUl, NavLi, FooterBrand } from 'flowbite-svelte';
</script>

<Navbar color="green" >
    <NavBrand href="/">
        <img src="/favicon.jpg" class="me-3 h-6 sm:h-9" alt="Festi pizza Logo" />
        <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Festi pizza</span>
    </NavBrand>
    <NavHamburger  />
    <NavUl nonActiveClass="text-gray-700 hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-green-700 dark:text-gray-400 md:dark:hover:text-green-400 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">
        <NavLi href="/">Accueil</NavLi>
        <NavLi href="/carte">Carte</NavLi>
        <NavLi href="/contact">Contact</NavLi>
    </NavUl>
</Navbar>

<main class="min-h-screen">
    <slot></slot>
</main>

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
