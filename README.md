# vuetify-form-dialog

[![Npm version](https://img.shields.io/npm/v/vuetify-form-dialog.svg?maxAge=2592000)](https://www.npmjs.com/package/vuetify-form-dialog)

## Usage

```HTML
<VFormDialog v-model="dialogVisible" @save="handleSave">
  <v-text-field v-model="firstName" label="First name"></v-text-field>
  <v-text-field v-model="lastName" label="Last name"></v-text-field>
</VFormDialog>
<v-btn @click="dialogVisible = true">Show</v-btn>
```

```javascript
import { VFormDialog } from 'vuetify-form-dialog'

export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      dialogVisible
    }
  },
  components: {
    VFormDialog
  },
  methods: {
    handleSave() {
      // Handle saving here
    }
  }
}
```

## API

### v-form-dialog 

#### slots 

- `default` 

- `beforeButtons` 

- `buttons` 

- `afterButtons` 

#### props 

- `buttons-right` ***Boolean*** (*optional*) 

- `cancel-button-color` ***String*** (*optional*) 

- `cancel-button-text` ***String*** (*optional*) `default: 'Cancel'` 

- `clear-button-color` ***String*** (*optional*) 

- `clear-button-text` ***String*** (*optional*) `default: 'Clear'` 

- `colored-buttons` ***Boolean*** (*optional*) 

- `dark-title` ***Boolean*** (*optional*) 

- `hide-cancel-icon` ***Boolean*** (*optional*) 

- `hide-cancel-button` ***Boolean*** (*optional*) 

- `hide-clear-button` ***Boolean*** (*optional*) 

- `hide-save-button` ***Boolean*** (*optional*) 

- `save-button-color` ***String*** (*optional*) 

- `save-button-text` ***String*** (*optional*) `default: 'Save'` 

- `title` ***String*** (*optional*) 

- `title-color` ***String*** (*optional*) `default: 'primary'` 

- `value` ***Boolean*** (*optional*) 

#### data 

- `formValid` 

**initial value:** `false` 

#### events 

- `clear` 

#### methods 

- `handleClear()` 

## Installation

```
npm install vuetify-form-dialog
```

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Run your tests

```
npm run test
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

### Update the API section of README.md with generated documentation

```
npm run doc:build
```
