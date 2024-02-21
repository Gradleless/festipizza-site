<script>
  import { Card, Listgroup, ListgroupItem } from 'flowbite-svelte';
</script>

<div class="flex justify-center items-center min-h-screen">
  <Card class="w-full max-w-md">
    <h5 class="text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Contactez-nous</h5>
    <p class="font-normal text-gray-700 dark:text-gray-400 mb-4">N'hésitez pas à nous contacter pour toute question ou information.</p>
    
    <Listgroup>
      <ListgroupItem>
        <div class="flex items-center">
          <div class="ml-3">
            <p class="text-base font-medium text-gray-900 dark:text-white">Téléphone</p>
            <p class="text-sm font-normal text-gray-500 dark:text-gray-400 dark:hover:text-green-400"><a href="tel:0320878196">+33 03 20 87 81 96</a></p>
          </div>
        </div>
      </ListgroupItem>
      <ListgroupItem>
        <div class="flex items-center">
          <div class="ml-3">
            <p class="text-base font-medium text-gray-900 dark:text-white">Adresse</p>
            <p class="text-sm font-normal text-gray-500 dark:text-gray-400 dark:hover:text-green-400"><a href="https://maps.app.goo.gl/oUMEfxz5VH8ouvbu7">15 Rue Pierre Ogée, 59112 Annœullin</a></p>
          </div>
        </div>
      </ListgroupItem>
    </Listgroup>
  </Card>
</div>

