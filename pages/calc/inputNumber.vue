<template>
  <v-row>
    <v-col sm="4" class="text-center">
      <v-text-field v-model="input" outlined filled type="number" label='ใส่ตัวเลข' />
    </v-col>
  </v-row>
</template>


<script>
export default {
  data() {
    return {
      input: null
    }
  },
  methods:{
    getNumber() {
      return this.input
    },
  }
}
</script>