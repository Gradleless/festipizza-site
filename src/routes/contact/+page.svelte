<script lang="ts">
  import { Card, Listgroup, ListgroupItem, Popover } from 'flowbite-svelte';
  import 'leaflet/dist/leaflet.css';

  function norman_thavaud() {

    const Lp = (import('leaflet'))
        Lp.then(L=>{
            const map = L.map("map", {
                center: [50.5286375, 2.9328349],
                zoom: 20
            });
            
            L.tileLayer('https://{s}.google.com/vt/lyrs=p&x={x}&y={y}&z={z}',{
                //maxZoom: 19,
                subdomains:['mt0','mt1','mt2','mt3'],
                attribution: '&copy; <a href="http://maps.google.com">Google Maps</a>'
            }).addTo(map);
        }).catch(() => {})
    }
  
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
        <div class="flex items-center" id="address">
          <div class="ml-3">
            <p class="text-base font-medium text-gray-900 dark:text-white">Adresse</p>
            <p class="text-sm font-normal text-gray-500 dark:text-gray-400 dark:hover:text-green-400"><a href="https://maps.app.goo.gl/aTYDXtWDKDiB11MD7">15 Rue Pierre Ogée, 59112 Annœullin</a></p>
            <Popover class="text-sm font-light w-96 " title="Nous sommes ici !" triggeredBy="#address" on:show={norman_thavaud} defaultClass=""><div id="map" class="h-64 rounded-b-md"></div></Popover>
          </div>
        </div>
      </ListgroupItem>
    </Listgroup>
  </Card>
</div>

