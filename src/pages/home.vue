<!-- eslint-disable vue/multi-word-component-names -->
<template>
	<div class="card__wrapper" v-for="item in items" :key="item.id">
		<Card
		:imgUrl="item.img"
		:name="`Lvl ${item.lvl}`"
		:title="item.title"
		:link="item.alias">
		{{item.descr}}
		</Card>
	</div>
</template>

<script>
	import Card from '@/components/UI/Card'
	import items from '@/seeders/items.js'
	export default {
		components: {Card},
	data() {
		return {
			items: items
		}
	}
	}
</script>
