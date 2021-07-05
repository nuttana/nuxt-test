<template>
<v-container>
  <v-row justify="center">
    <v-text-field v-model="input" label='ข้อความ' />
  </v-row>
	<v-row justify="center">
		<v-btn @click="postData" color="primary"> SEND </v-btn>
	</v-row>
	<v-data-table
    :headers="headers"
    :items="dataArray"
  ></v-data-table>

</v-container>
</template>

<script>
export default {
	data() {
		return {
			input: '',
			dataArray: [],
			headers: [
        {
          text: 'ข้อความ',
          value: 'msg',
        },
        { text: 'ขนาด',
					value: 'length'
				},
      ],
		}
	},
	methods: {
		async postData() {
			const res = await this.$axios.$post('http://localhost:4000/exam', {data: this.input})
			this.input = ''
			this.dataArray.push(res)
		}
	}
}
</script>