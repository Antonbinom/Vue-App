<!-- eslint-disable vue/valid-template-root -->
<template>
	<div class="wrapper">
		<div v-if="item" class="card card-single">
			<img :src="item.img" :alt="item.title">
			<h1 class="title">{{item.title}}</h1>
			<p>{{item.descr}}</p>
			<div class="card-button">
				<router-link class="btn btnPrimary" to="/">Назад</router-link>
			</div>
		</div>
	</div>
</template>

<script>
import items from '@/seeders/items.js'
export default {
	data () {
		return {
			item: null
		}
	},
	created () {
		const alias = this.$route.params.itemAlias;
		const item = items.find(el=>el.alias === alias);
		this.item = item;
	}

}
</script>