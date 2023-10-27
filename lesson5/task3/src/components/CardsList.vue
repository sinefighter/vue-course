<template>
	<div class="row">
		<card-item 
			:laptop="laptop" 
			v-for="laptop in laptops" :key="laptop.id"
		/>
	</div>
</template>

<script>
	import { laptops } from '@/data/laptops'
	import CardItem from './CardItem.vue'

	export default {
		name: 'CardsList',
		components: {
			CardItem
		},
		data() {
			return {
				laptops
			}
		}
	}
</script>

<style lang="scss" scoped>

</style>