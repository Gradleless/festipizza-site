<script lang="ts">
    import { FloatingLabelInput, P, Toast, Card, Heading, Button, Pagination } from 'flowbite-svelte';
    import { ArrowRightOutline } from 'flowbite-svelte-icons';
    import Carte from './carte/carte.svelte';
</script>  

<div class="text-left md:pl-24 max-sm:text-center pb-28 bg-no-repeat bg-cover" style="background-image: url('/resto.jpg');">
    <Heading tag="h1" class="mb-4 pt-32" customSize="text-4xl font-extrabold  md:text-5xl lg:text-6xl">We invest in the world’s potential</Heading>
    <P class="mb-6 text-lg lg:text-xl dark:text-gray-400 text-left md:mr-96 max-sm:text-center">Here at Flowbite we focus on markets where technology, innovation, and capital can unlock long-term value and drive economic growth.</P>
    <Button href="/carte" color="green">
        Regardez la carte
        <ArrowRightOutline class="w-3.5 h-3.5 ms-2" />
    </Button>
</div>

<Carte />