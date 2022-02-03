<template>
  <form>
    <h2 class="label-wrapper">
        <label class="label__lg" for="Temperature in Centigrade">
            °C
        </label>
    </h2>
    <input
      type="float"
      class="input__lg"
      id="cent-temp"
      name="cent-temp"
      autocomplete="off"
      v-model="centigrade"
      :placeholder="(fahrenheit - 32) * 5/9"
      v-on:keyup="clearFahr"
    />

    <h2 class="label-wrapper">
        <label class="label__lg" for="Temperature in Fahrenheit">
            °F
        </label>
    </h2>
    <input
      type="float"
      class="input__lg"
      id="fahr-temp"
      name="fahr-temp"
      autocomplete="off"
      v-model="fahrenheit"
      :placeholder="(centigrade * 9/5) + 32"
      v-on:keyup="clearCent"
    />

  </form>
  
</template>

<script>
    export default {

        data: () => ({
            centigrade: 20,
            fahrenheit: '',
        }),

        methods: {

            clearFahr () {
                this.fahrenheit = ''
            },

            clearCent () {
                this.centigrade = ''
            },
        }

    }
</script>


