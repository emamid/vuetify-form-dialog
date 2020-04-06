<template>
    <v-dialog v-model="value">
		<v-dialog-header 
			:darkTitle="darkTitle" 
			:hideCancelIcon="hideCancelIcon" 
			:title="title" 
			:titleColor="titleColor" 
			@click="cancel"
		/>
		<v-card>
			<v-card-text>
				<slot/>			
			</v-card-text>
			<v-dialog-footer 
				:buttonsRight="buttonsRight" 
				:cancelButtonColor="cancelButtonColor" 
				:cancelButtonText="cancelButtonText" 
				:clearButtonText="clearButtonText"
				:clearButtonColor="clearButtonColor"
				:coloredButtons="coloredButtons"
				:hideCancelButton="hideCancelButton"
				:hideClearButton="hideClearButton"
				:hideSaveButton="hideSaveButton"
				:isValid="isValid"
				:saveButtonColor="saveButtonColor"
				:saveButtonText="saveButtonText"
				@cancel="cancel"
				@clear="clear"
				@save="save"
			>
				<template slot="beforeButtons"><slot name="beforeButtons"/></template>
				<template slot="buttons"><slot name="buttons"/></template>
				<template slot="afterButtons"><slot name="afterButtons"/></template>
			</v-dialog-footer>
		</v-card>
	</v-dialog>
</template>

<script>

import VDialogFooter from './VDialogFooter';
import VDialogHeader from './VDialogHeader';

export default {
	name: 'VDialogWrapper',
	components: {
		VDialogFooter,
		VDialogHeader
	},
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
		value: {
			type: Boolean, 
			default: true
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
