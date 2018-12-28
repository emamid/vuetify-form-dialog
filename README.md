# vuetify-form-dialog

[![Npm version](https://img.shields.io/npm/v/vuetify-form-dialog.svg?maxAge=2592000)](https://www.npmjs.com/package/vuetify-form-dialog)

## Usage

```HTML
<VFormDialog :text="hello"></VFormDialog>
```

```javascript
import { VFormDialog } from 'vuetify-form-dialog'

export default {
  components: {
    VFormDialog
  }
}
```

## API

### v-form-dialog 

#### slots 

- `default` 

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
