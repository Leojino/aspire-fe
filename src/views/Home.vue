<template>
<q-page class=" flex flex-center bg-blue-1">
  <div class="home">
    <div class="row">
      <div class="col">
        <transition name="quickloan-starter">
        <q-card class="quick-loan-card" v-if="!sentForApproval">
          <q-card-section>
            <div class="text-h5">Start a new loan</div>
            <q-input v-model="quickLoan" type="number" label="Amount Required" step="1000" min="10000" />
            <q-input v-model="quickLoanTerm" type="number" label="Loan Term (In Months)" step="1" min="3" />
            <div v-if="quickLoan && quickLoanTerm" class="q-mt-lg">
              Alright, lets get started
              <div class="q-mt-lg">
                <span>Payment frequency: </span><span class="text-bold">Weekly</span>
              </div>
              <div class="q-mt-lg">
                <q-btn align="left" class="btn-fixed-width" color="primary" label="Submit Request" @click="sentForApproval = true"/>
              </div>
            </div>
          </q-card-section>
        </q-card>
        </transition>
        
        <transition name="quickloan-application">
        <q-card class="quick-loan-card" v-if="sentForApproval">
          <q-card-section>
            <div class="text-h5">Loan Approved</div>
            <div class="q-mt-lg">
              <span>Weekly payment of <span class="text-bold">{{ paymentAmount }}</span> from {{ quickLoanTerm }} months.</span>
            </div>
            <div class="q-mt-lg">
              <q-btn align="left" class="btn-fixed-width" color="primary" label="Resubmit Request" @click="sentForApproval = false"/>
            </div>
          </q-card-section>
        </q-card>
        </transition>
      </div>
    </div>
  </div>
</q-page>
</template>

<script>
import {ref} from 'vue';

export default {
  name: 'Home',
  setup() {
    return {
      quickLoan: ref(null),
      quickLoanTerm: ref(null),
      sentForApproval: ref(false)
    }
  },
  computed: {
    paymentAmount() {
      return (this.quickLoan / this.quickLoanTerm).toFixed(1);
    }
  }
}
</script>

<style lang="scss">
.quick-loan-card{
  max-width: 100%;
  width: 500px;
  transition: all .5s ease-in-out;
}

.quickloan-starter-enter-from {
  opacity: 0;
  transform: translateY(-100px);
}
.quickloan-starter-enter-to {
  opacity: 1;
  transform: translateY(0px);
}

.quickloan-starter-leave-from {
  opacity: 1;
  transform: translateY(0px);
}
.quickloan-starter-leave-to {
  opacity: 0;
  transform: translateY(-100px);
}

.quickloan-application-enter-from {
  position: absolute;
  opacity: 0;
  transform: translateY(120px);
}
.quickloan-application-enter-to {
  position: relative;
  opacity: 1;
  transform: translateY(0px);
}
.quickloan-application-leave-from {
  position: relative;
  opacity: 1;
  transform: translateY(0px);
}
.quickloan-application-leave-to {
  position: absolute;
  opacity: 0;
  transform: translateY(120px);
}


</style>
