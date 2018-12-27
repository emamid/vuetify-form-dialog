<template>
    <FormDialog :value="value" @input="(value) => $emit('input', value)" title="Test Dialog" coloredButtons buttonsRight>
        <v-layout row wrap>
            <v-flex xs4>
                <v-text-field v-model="person.firstName" label="First name" required :rules="rules.name"/>
            </v-flex>
            <v-flex xs4>
                <v-text-field v-model="person.lastName" label="Last name" required :rules="rules.name"/>
            </v-flex>
        </v-layout>
    </FormDialog>    
</template>

<script>

import VFormDialog from '@/components/FormDialog'

export default {
    data() {
        return {
            person: {
                firstName: '',
                lastName: ''
            },
            rules: {
                name: [
                    v => !!v || 'Name is required',
                    v => (v && v.length >= 2) || 'Name must be at least 2 characters'
                ]
            }
        }
    },
    props: {
        value: Boolean
    },
    components: {
        FormDialog
    }
}

</script>

