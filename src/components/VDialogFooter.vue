<template>
	<v-card-actions>
		<v-spacer v-if="buttonsRight"/>
		<slot name="beforeButtons"/>
		<slot name="buttons">
			<v-btn v-if="!hideSaveButton" :color="$saveButtonColor" :disabled="!isValid" @click="$emit('save')">{{saveButtonText}}</v-btn>
			<v-btn v-if="!hideCancelButton" :color="$cancelButtonColor" @click="$emit('cancel')">{{cancelButtonText}}</v-btn>
			<v-btn v-if="!hideClearButton" :color="$clearButtonColor" @click="$emit('clear')">{{clearButtonText}}</v-btn>
		</slot>
		<slot name="afterButtons"/>
	</v-card-actions>
</template>

<script>
export default {
	name: 'VDialogFooter',
	props: {
		buttonsRight: Boolean,
		cancelButtonColor: String,
		cancelButtonText: {
			type: String,
			default: 'Cancel'
		},
		clearButtonColor: String,
		clearButtonText: {
			type: String,
			default: 'Clear'
		},
		coloredButtons: Boolean,
		hideCancelButton: Boolean,
		hideClearButton: Boolean,
		hideSaveButton: Boolean,
		isValid: Boolean,
		saveButtonColor: String,
		saveButtonText: {
			type: String,
			default: 'Save'
		}
	},
	computed: {
		$cancelButtonColor() {
			return this.cancelButtonColor ? this.cancelButtonColor : (this.coloredButtons ? 'error' : 'primary');
		},
		$clearButtonColor() {
			return this.clearButtonColor ? this.clearButtonColor : (this.coloredButtons ? 'warning' : 'primary');
		},
		$saveButtonColor() {
			return this.saveButtonColor ? this.saveButtonColor : (this.coloredButtons ? 'success' : 'primary');
		}
	}
}
</script>
