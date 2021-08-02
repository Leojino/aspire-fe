<template>
  <q-layout view="lHh Lpr lFf">
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      class="bg-primary text-white"
    >
        <div class="q-mt-xl q-ma-lg">
            <img
                alt="Aspire"
                src="./assets/logo.svg"
                style="width: 150px; height: 50px"
            />
            <div>Trusted way of banking for 3,000+ SMEs and startups in Singapore</div>
        </div>

        <q-list class="q-mt-xl">
            <q-item clickable class="q-mt-lg q-mb-lg" :active="$route.name == 'Home'" active-class="text-green-4">
                <q-item-section avatar>
                    <img src="./assets/Home.svg" />
                </q-item-section>
                <q-item-section>
                  <router-link to="/" style="text-decoration: none; color: inherit;">Home</router-link>
                </q-item-section>
            </q-item>
            <q-item clickable class="q-mt-lg q-mb-lg" :active="$route.name == 'Cards'" active-class="text-green-4">
                <q-item-section avatar>
                    <img src="./assets/Card.svg" />
                </q-item-section>
                <q-item-section class="">
                  <router-link to="/cards" style="text-decoration: none; color: inherit;">Cards</router-link>
                </q-item-section>
            </q-item>
            <q-item clickable class="q-mt-lg q-mb-lg" active-class="text-green-4">
                <q-item-section avatar>
                    <img src="./assets/Payments.svg" />
                </q-item-section>
                <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable class="q-mt-lg q-mb-lg" active-class="text-green-4">
                <q-item-section avatar>
                    <img src="./assets/Credit.svg" />
                </q-item-section>
                <q-item-section>Credits</q-item-section>
            </q-item>
            <q-item clickable class="q-mt-lg q-mb-lg" active-class="text-green-4">
                <q-item-section avatar>
                    <img src="./assets/Account.svg" />
                </q-item-section>
                <q-item-section>Settings</q-item-section>
            </q-item>
        </q-list>
    </q-drawer>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from "vue";

export default {
  name: "App",


  setup() {
    
    return {
      leftDrawerOpen: ref(false),
    };
  },
  mounted() {
    console.log(this.$route.name)
  }
};
</script>
