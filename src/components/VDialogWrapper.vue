<template>
    <v-dialog v-model="value">
		<v-toolbar :color="titleColor" :dark="darkTitle">
			<v-toolbar-title>{{title}}</v-toolbar-title>
			<v-spacer v-if="!hideCancelIcon"/>
			<v-btn v-if="!hideCancelIcon" icon @click="cancel">
				<v-icon>clear</v-icon>
			</v-btn>
		</v-toolbar>
		<v-card>
			<v-card-text>
				<slot/>			
			</v-card-text>
			<v-card-actions>
				<v-spacer v-if="buttonsRight"/>
				<slot name="beforeButtons"/>
				<slot name="buttons">
					<v-btn v-if="!hideSaveButton" :color="$saveButtonColor" :disabled="!isValid" @click="save">{{saveButtonText}}</v-btn>
					<v-btn v-if="!hideCancelButton" :color="$cancelButtonColor" @click="cancel">{{cancelButtonText}}</v-btn>
					<v-btn v-if="!hideClearButton" :color="$clearButtonColor" @click="clear">{{clearButtonText}}</v-btn>
				</slot>
				<slot name="afterButtons"/>
			</v-card-actions>
		</v-card>
	</v-dialog>
</template>

<script>

export default {
	name: 'VDialogWrapper',
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
		darkTitle: Boolean,
		hideCancelIcon: Boolean,
		hideCancelButton: Boolean,
		hideClearButton: Boolean,
		hideSaveButton: Boolean,
		isValid: Boolean,
		saveButtonColor: String,
		saveButtonText: {
			type: String,
			default: 'Save'
		},
		title: String,
		titleColor: {
			type: String,
			default: 'primary'
		},
		value: Boolean
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
	},
	methods: {
		cancel() {
			this.$emit('cancel');
			this.$emit('close');
			this.$emit('input', false);
		},
		clear() {
			this.$emit('clear');
		},
		save() {
			this.$emit('save');
			this.$emit('close');
			this.$emit('input', false);
		}
	}
}

</script>
