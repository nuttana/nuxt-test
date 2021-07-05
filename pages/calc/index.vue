<template>
  <v-row justify="center" align="center">
    <v-col class="text-xs-center">
      <inputNumber ref="input"/>
      <Calculate :input="input" @call="getNumber"/>
    </v-col>
  </v-row>
</template>

<script>
import inputNumber from "~/pages/calc/inputNumber.vue";
import Calculate from "~/components/Calculate.vue"

export default {
  components: {
    inputNumber,
    Calculate,
  },
  data() {
    return {
      input: null,
    }
  },
  methods: {
    getNumber() {
      this.input = this.$refs.input.getNumber()
    }
  }
};
</script>
