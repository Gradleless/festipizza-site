<script lang="ts">
    import { P, Heading, Button } from 'flowbite-svelte';
    import { ArrowRightOutline } from 'flowbite-svelte-icons';
    import Carte from './carte/carte.svelte';
</script>  

<div class="text-left md:pl-24 max-sm:text-center pb-28 bg-no-repeat bg-[url('/festi.webp')] bg-left-top lg:bg-cover">
    <Heading tag="h1" class="mb-4 pt-32" customSize="text-4xl font-extrabold  md:text-5xl lg:text-6xl">Découvrez des saveurs authentiques à Annoeullin</Heading>
    <P class="mb-6 text-lg lg:text-2xl text-left md:mr-96 max-sm:text-center">Chez Festi pizza, nous mettons l'accent sur des ingrédients de qualité et des recettes traditionnelles pour vous offrir une expérience gustative incomparable.</P>
    <Button href="/carte" color="green">
        Regardez la carte
        <ArrowRightOutline class="w-3.5 h-3.5 ms-2" />
    </Button>
</div>

<Carte />
