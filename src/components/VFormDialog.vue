<template>
    <VDialogWrapper ref="dialog" :value="value" @input="(value) => $emit('input', value)"
        :buttonsRight="buttonsRight" 
        :cancelButtonColor="cancelButtonColor" 
        :cancelButtonText="cancelButtonText" 
        :clearButtonText="clearButtonText"
        :coloredButtons="coloredButtons"
        :hideCancelIcon="hideCancelIcon"
        :hideCancelButton="hideCancelButton"
        :hideClearButton="hideClearButton"
        :hideSaveButton="hideSaveButton"
        :isValid="formValid"
        :saveButtonColor="saveButtonColor"
        :saveButtonText="saveButtonText"
        :title="title"
        :titleColor="titleColor"
        :darkTitle="darkTitle"
        @cancel="$emit('cancel')"
        @clear="handleClear"
        @close="$emit('close')"
        @save="$emit('save')"
    >
        <v-form ref="form" v-model="formValid">
            <slot/>
        </v-form>
        <template slot="beforeButtons"><slot name="beforeButtons"/></template>
        <template slot="buttons"><slot name="buttons"/></template>
        <template slot="afterButtons"><slot name="afterButtons"/></template>
    </VDialogWrapper>
</template>

<script>

import VDialogWrapper from './VDialogWrapper'

export default {
	name: 'VFormDialog',
    data() {
        return {
            formValid: false
        }
    },
    components: {
        VDialogWrapper
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
    methods: {
        handleClear() {
            this.$refs.form.reset();
            this.$emit('clear');
        }
    }
}

</script>

