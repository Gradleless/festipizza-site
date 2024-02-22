<script lang="ts">
    import { FloatingLabelInput, Card, Heading, Pagination } from 'flowbite-svelte';
    import data from '$lib/carte.json';
    import { onMount } from 'svelte';

    interface CarteItem {
        name: string;
        price: number;
        description: string;
        image: string;
        isNew: boolean;
    }

    let pages = [
        { name: "Pizza" },
        { name: "Pâtes" },
        { name: "Desserts" }];

    let dataCarte: { category: string, items: CarteItem[] }[] = []; 
    let allData: { category: string, items: CarteItem[] }[] = [];

    // Récupérer les données de la carte
    function getCarte() {
        for (let [cat, items] of Object.entries(data)) {
            let catItems: CarteItem[] = [];

            for(let item of items) {
                catItems = [...catItems, { name: item.nom, price: item.prix, description: item.description, image: item.image, isNew: true}];
            }
            dataCarte.push({ category: cat, items: catItems });
        }
    }

    getCarte();
    allData = dataCarte;

    // Filtrer les produits de la carte
    const handleClick = (e: Event) => {
        dataCarte = allData.filter(item => item.category === (e.target as HTMLElement).innerText);
    };

     // pas moyen  de faire autrement, il y a pas d'event pour previous et next
    const next = () => {
        dataCarte = allData.filter(item => item.category === "Boissons");
    }

    const previous = () => {
        dataCarte = allData;
    } 

    // Chercher un produit dans la carte
    onMount(() => {
        const floatingOutlined = document.getElementById("floating_outlined");

        if (floatingOutlined) {
            floatingOutlined.addEventListener("input", function(e) {
                let search = (e.target as HTMLInputElement).value;

                dataCarte = allData.map(item => {
                    let items = item.items.filter(i => i.description.toLowerCase().includes(search.toLowerCase()) || i.name.toLowerCase().includes(search.toLowerCase()));
                    return { category: item.category, items: items };
                });
            });
        }
    });
</script>  

<Heading class="text-center dark:text-green-500 mb-6 mt-16 text-4xl" id="card">Notre carte</Heading>

<div class="align-middle md:mx-96 my-6 max-sm:mx-8">
    <FloatingLabelInput style="outlined" id="floating_outlined" name="floating_outlined" type="text" color="green">
        Chercher un produit
    </FloatingLabelInput>
</div>

<Pagination {pages} large class="flex justify-center flex-wrap" on:click={handleClick} on:previous={previous} on:next={next}>
    <svelte:fragment slot="prev">
        Tout
    </svelte:fragment>  
    <svelte:fragment slot="next">
        Boissons
    </svelte:fragment>
</Pagination>

<div class="grid md:grid-cols-3 md:mx-32">
    {#each dataCarte as data (data.category)}
        {#each data.items as { name, price, description, image, isNew } (name)}

            <div class="card mx-5" class:scale-transition={isNew}>
                <Card img={image} class="my-5 object-contain" href="#card" size="sm">
                    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{name}</h5>
                    <h4 class="mb-2 text-xl font-bold tracking-tight text-green-500 dark:text-green-400">{price} €</h4>
                    <p class="h-8 text-gray-700 dark:text-gray-400 leading-tight">{description}</p>
                </Card>
            </div>

        {/each}
    {/each}
</div>

<style>
    .scale-transition {
        animation: scaleIn 300ms forwards;
    }

    @keyframes scaleIn {
        from { transform: scale(0.5); }
        to { transform: scale(1); }
    }
</style>