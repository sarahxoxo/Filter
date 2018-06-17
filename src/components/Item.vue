<template>
	<div class="item d-flex align-items-center">
		<div class="img">
			<img :src="item.Picture1">
		</div>
		<div class="content">
			<div class="title">
				{{ item.Name }}
			</div>
			<p>{{ item.Description }}</p>
			<div class="d-flex align-baseline">
				<div class="company">{{ item.Tel }}</div>
				<div v-if="item.Ticketinfo" class="tag">{{ item.Ticketinfo }}</div>
				<div class="tag">{{ item.Zone }}</div>
			</div>
			<div class="info">
				<div class="place"><i class="fas fa-map-marker-alt"></i>{{ item.Add }}</div>
				<div class="date"><i class="far fa-calendar-alt"></i>{{ item.Opentime }}</div>
			</div>
		</div>
	</div>
</template>
<script>
export default {
	name: 'Item',
  	props: ['item']
}
</script>
<style scoped>
.item {
	margin-top: 24px;
	background: #fff;
    /*width: 780px;*/
}
.img {
	flex: 0 0 22%;
}
.content {
    padding: 24px 20px;
}
.title {
	font-size: 24px;
	color: var(--sec-color);
	line-height: 36px;
	font-weight: bold;
}
.content p {
	font-size: 16px;
	line-height: 24px;
}
.company {
	font-size: 16px;
	font-weight: bold;
	margin-right: 12px;
}
.tag {
	background: var(--dark-grey);
	color: #fff;
	border-radius: 100px;
	font-style: italic;
	font-size: 16px;
	padding: 2px 16px;
	margin-right: 12px;
	font-weight: 300;
}
.info {
	margin-top: 16px;
	color: var(--darker-grey);
}
.place {
    margin: 0 20px 10px 0;
}
.place i, .date i {
	color: #000;
	margin-right: 7px;
}
</style>