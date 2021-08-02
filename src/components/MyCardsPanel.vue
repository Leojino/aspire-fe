<template>
  <div>
    <div class="row">
      <div class="col">
        <div class=""></div>
        <q-carousel
          v-model="slide"
          transition-prev="slide-right"
          transition-next="slide-left"
          animated
          control-color="green-7"
          class="rounded-borders cards-carousel"
          navigation
        >
          <q-carousel-slide name="style" class="column no-wrap">
            <q-card dark bordered class="bg-green-7 my-card shadow-5">
              <q-card-section>
                <div class="flex justify-end">
                  <img
                    src="../assets/aspire_logo_white.svg"
                    class="my-card-logo"
                  />
                </div>
                <div class="text-h5 q-mt-sm">Mark Henry</div>
                <div class="my-card-no-block">
                  <span class="no-hidden">****</span>
                  <span class="no-hidden">****</span>
                  <span class="no-hidden">****</span>
                  <span>2020</span>
                </div>
                <span class="inline-block q-ma-sm">Thru: 12/20</span>
                <span class="inline-block q-ma-sm">CVV: ***</span>
                <div class="flex justify-end">
                  <img src="../assets/visa_logo.svg" class="my-card-logo" />
                </div>
              </q-card-section>
            </q-card>
          </q-carousel-slide>
        </q-carousel>
      </div>
      <div class="col">
        <q-list
          bordered
          class="no-border rounded-borders shadow-1 bg-blue-2 q-mt-md"
        >
          <q-expansion-item>
            <template v-slot:header>
              <q-item-section avatar>
                <q-avatar icon="fact_check" text-color="black" />
              </q-item-section>

              <q-item-section> Card Details </q-item-section>
            </template>

            <q-card>
              <q-card-section> The entire card details </q-card-section>
            </q-card>
          </q-expansion-item>
        </q-list>
        <q-list
          bordered
          class="no-border rounded-borders shadow-1 bg-blue-2 q-mt-md"
        >
          <q-expansion-item>
            <template v-slot:header>
              <q-item-section avatar>
                <q-avatar icon="swap_horiz" text-color="black" />
              </q-item-section>

              <q-item-section> Recent transactions </q-item-section>
            </template>

            <q-card>
              <q-list bordered class="rounded-borders" style="">

                <q-item clickable v-ripple>
                  <q-item-section avatar>
                    <q-avatar>
                      <q-avatar icon="shopping_bag" text-color="black" />
                    </q-avatar>
                  </q-item-section>

                  <q-item-section>
                    <q-item-label lines="1">Hamley's</q-item-label>
                    <q-item-label caption lines="1">
                      20 May 2020
                      <div class="text-weight-bold">Refund on debit card</div>
                    </q-item-label>
                  </q-item-section>

                  <q-item-section side top> + $150 </q-item-section>
                </q-item>

              </q-list>
            </q-card>
          </q-expansion-item>
        </q-list>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "MyCardsPanel",
  setup() {
    return {
      slide: ref("style"),
    };
  },
};
</script>

<style lang="scss" scoped>
.cards-carousel {
  height: 300px;
}
.my-card {
  height: 220px;
}
.my-card-logo {
  width: 80px;
}
.my-card-no-block {
  font-size: 20px;
  margin-top: 10px;
}
.my-card-no-block > span {
  display: inline-block;
  margin: 0 8px;
  width: 65px;
  vertical-align: middle;
}
.my-card-no-block .no-hidden {
  letter-spacing: 5px;
}
</style>