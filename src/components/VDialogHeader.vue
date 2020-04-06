<template>
	<v-toolbar :color="titleColor" :dark="darkTitle">
		<v-toolbar-title>{{title}}</v-toolbar-title>
		<v-spacer v-if="!hideCancelIcon"/>
		<v-btn v-if="!hideCancelIcon" icon @click="$emit('cancel')">
			<v-icon>clear</v-icon>
		</v-btn>
	</v-toolbar> 
</template>

<script>
export default {
	name: 'VDialogHeader',
	props: {
		darkTitle: Boolean,
		hideCancelIcon: Boolean,
		title: String,
		titleColor: {
			type: String,
			default: 'primary'
		}
	}
}
</script>
