<template>
  <pv-toast/>
  <header >
    <pv-toolbar class="bg-primary">
      <template #start>
        <h3>VaRuta</h3>
      </template>

      <template #end>
        <div class="flex-column">
          <router-link v-for="item in items"
                       v-model:to="item.to"
                       custom
                       v-slot="{navigate, href, isActive}"
                       v-model:key="item.label">

            <pv-button class="p-button-text text-white"
               v-bind:href="href"
                @click="navigate">{{ item.label }}
            </pv-button>
          </router-link>
        </div>
      </template>
    </pv-toolbar>
  </header>
  <pv-sidebar v-model:visible="drawer"></pv-sidebar>
  <router-view></router-view>
</template>

<script >
import { RouterLink, RouterView } from 'vue-router'
export default {
  data() {
    return {
      drawer: false,
      items: [

        { label: 'Home', to: '/home' },
        { label: 'Senders', to: '/senders' },
        { label: 'Consignees', to: '/consignees' },
        { label: 'Destinations', to: '/destinations' },
        { label: 'Type of document', to: '/documents' },
        { label: 'Shippings', to: '/shipping' },
        { label: 'Order Delivery', to: '/deliver' },
        { label: 'Shipping Status', to: '/status' },

      ]
    }
  }
}
</script>


<style scoped>
</style>
