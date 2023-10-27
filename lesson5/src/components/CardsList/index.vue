<template>
	<div class="row">
		<card-item 
			:berry="berry" 
			v-for="berry in berries" :key="berry.id"
		/>
	</div>
</template>

<script>
	import { berries } from '@/data/berries'
	import CardItem from './CardItem.vue'

	export default {
		name: 'CardsList',
		components: {
			CardItem
		},
		data() {
			return {
				berries
			}
		}
	}
</script>

<style lang="scss" scoped>

</style>