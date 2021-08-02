<template>
  <q-page class="q-pa-xl">
    <div class="text-h6">Available balance</div>
    <div class="flex justify-between">
      <span class="flex align-center">
        <q-chip square color="green" text-color="white">$</q-chip>
        <span style="font-size: 27px">3,000</span>
      </span>
      <q-btn
        unelevated
        color="primary"
        label="New Card"
        size="sm"
        icon="add_circle"
        class="q-pa-sm"
        style="font-size: 14px"
      />
    </div>

    <q-tabs v-model="tab" align="left" class="text-teal">
      <q-tab
        :ripple="false"
        content-class="text-capitalize text-black"
        name="myCards"
        label="My debit cards"
      />
      <q-tab
        :ripple="false"
        content-class="text-capitalize text-black"
        name="allCards"
        label="All company cards"
      />
    </q-tabs>
    <q-tab-panels v-model="tab" animated class="shadow-2 rounded-borders q-mt-md">
      <q-tab-panel name="myCards">
        <MyCardsPanel/>
      </q-tab-panel>

      <q-tab-panel name="allCards">
        <MyCardsPanel/>
      </q-tab-panel>
    </q-tab-panels>
  </q-page>
</template>

<style lang="scss">
.card-page-tabs {
  padding: 5px 7px;
}
</style>

<script>
import { ref } from "vue";
import MyCardsPanel from '../components/MyCardsPanel.vue';

export default {
  setup() {
    return {
      tab: ref("myCards"),
    };
  },
  name: "CardsPage",
  components: {
      MyCardsPanel
  }
};
</script>
