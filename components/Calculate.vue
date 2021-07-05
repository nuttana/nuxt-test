<template>
<v-container>
  <v-row>
    <v-col sm="2" class="text-center">
      <v-btn color="primary" @click="call"> CALCULATE </v-btn>
    </v-col>
  </v-row>
	<v-row>
		<v-col sm="4" class="text-center">
      <v-text-field disabled filled outlined v-model="result" label="ผลลัพท์" />
    </v-col>
	</v-row>
</v-container>
</template>


<script>
export default {
  props: {
		input: {
			type: String,
			default: '',
		},
	},
  data() {
    return {
			result: '',
    }
  },
	watch: {
		input() {
			this.calc()
		},
	},
  methods:{
    call() {
      this.$emit('call', '')
    },
		calc() {
			if (isNaN(this.input)) return
			this.result = this.input / 100
		}
  }
}
</script>