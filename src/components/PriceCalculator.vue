<template>
  <div class="container">
    <div class="content-wrapper">
      <div class="header">
        <h1 class="logo"> <span class="purple">guaranteed</span><span class="gray">more</span> </h1>
        <p class="sub-header"> valuation approximator </p>
        <p> disclaimer - notice </p>
        <p> the purpose of this approximator is as a general indicator ONLY and does NOT form part of any formal offer.
        </p>
        <p> <strong> this facility is intended exclusively for the use of GM Partners only </strong> </p>
      </div>
      <div class="fields">
        <!-- User Input -->
        <div class="input-wrapper">
          <div class="input-prefix">GM</div>
          <div class="currency-symbol">£</div>
          <input type="number"
                 v-model="userEntry">
        </div>
        <!-- Condition A -->
        <div class="input-wrapper">
          <div class="vehicle-condition">A</div>
          <div class="input-prefix static">GM</div>
          <div class="currency-symbol">£</div>
          <input type="number"
                 v-model="computedValues.condition_a"
                 disabled>
        </div>
        <!-- Condition B -->
        <div class="input-wrapper">
          <div class="vehicle-condition">B</div>
          <div class="input-prefix static">GM</div>
          <div class="currency-symbol">£</div>
          <input type="number"
                 v-model="computedValues.condition_b"
                 disabled>
        </div>
        <!-- Condition C -->
        <div class="input-wrapper">
          <div class="vehicle-condition">C</div>
          <div class="input-prefix static">GM</div>
          <div class="currency-symbol">£</div>
          <input type="number"
                 v-model="computedValues.condition_c"
                 disabled>
        </div>
        <!-- Condition D -->
        <div class="input-wrapper">
          <div class="vehicle-condition">D</div>
          <div class="input-prefix static">GM</div>
          <div class="currency-symbol">£</div>
          <input type="number"
                 v-model="computedValues.condition_d"
                 disabled>
        </div>
      </div>
      <div class="footer">
        <p class="sub-header disclaimer"> INTERNAL USE ONLY </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PriceCalculator',
  data() {
    return {
      userEntry: 0,
      computedValues: {
        condition_a: 0,
        condition_b: 0,
        condition_c: 0,
        condition_d: 0,
      },
    }
  },
  mounted() {
    this.calculateInitialValues();
  },
  watch: {
    userEntry: function () {
      this.calculateInitialValues();
    },
  },
  methods: {
    calculateInitialValues() {
      this.computedValues.condition_a = Number((this.userEntry - (this.userEntry * 0.1)) - 800).toFixed(2);
      this.computedValues.condition_b = Number((this.userEntry - (this.userEntry * 0.13)) - 800).toFixed(2);
      this.computedValues.condition_c = Number((this.userEntry - (this.userEntry * 0.17)) - 800).toFixed(2);
      this.computedValues.condition_d = Number((this.userEntry - (this.userEntry * 0.22)) - 800).toFixed(2);
    },
  },
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}

.container .content-wrapper {
  padding: 10px;
}

.container .content-wrapper .header .logo {
  color: gray;
  font-size: 36px;
}

.container .content-wrapper .header .sub-header {
  font-size: 26px;
}

.container .content-wrapper .footer .sub-header.disclaimer {
  font-size: 32px;
  font-weight: 600;
  color: red;
}

.container .content-wrapper .fields {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 20px;
}
</style>
