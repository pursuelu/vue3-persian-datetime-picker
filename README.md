# vue3-persian-datetime-picker

[![npm version](https://badge.fury.io/js/vue-persian-datetime-picker.svg)](https://www.npmjs.com/package/vue-persian-datetime-picker)

> A vue3 plugin to select jalali date and time from [vue-persian-datetime-picker](https://talkhabi.github.io/vue-persian-datetime-picker)
> Migration from [vue-persian-datetime-picker](https://talkhabi.github.io/vue-persian-datetime-picker)


## Run this project

```shell
# 安装依赖
yarn
# OR
npm install

# 启动服务
yarn serve
# OR
npm run serve
```

## Migration files

    1、VuePersianDatetimePicker.vue: 
        ① model=>modelValue 
        ② emit(input) => this.$emit('update:modelValue',val) 
        ③ Annotation this.$forceUpdate() // maybe will make a bug
    2、style.scss: [disabled]=>[disabled='true'] ... 
    'xxxdisabled' couldn't process
    3、_transitions.scss：-leave-to.. -enter => -leave-to.. -enter-from

### Usage

main.js
```javascript
import VuePersianDatetimePicker from '@/components/picker/VuePersianDatetimePicker.vue'
// import VuePersianDatetimePicker from 'vue-persian-datetime-picker'
import { createApp } from 'vue'
import App from './App.vue'
const app = createApp(App)
app.component('date-picker', VuePersianDatetimePicker)
app.mount('#app')

//...
```
Or in component
```html
<template>
    <div>
        <date-picker v-model="date"></date-picker>
    </div>
</template>
 
<script>
    // import VuePersianDatetimePicker from 'vue-persian-datetime-picker'
    import VuePersianDatetimePicker from '@/components/picker/VuePersianDatetimePicker.vue'
    export default {
      setup() {
        const date = ''
        return {
          date
        }
      },
      components: {
        datePicker: VuePersianDatetimePicker
      }
    }
</script>
```


## You can also set default values: 
main.js
```javascript

// import VuePersianDatetimePicker from 'vue-persian-datetime-picker'
import VuePersianDatetimePicker from '@/components/picker/VuePersianDatetimePicker.vue''
import { createApp } from 'vue'
import App from './App.vue'
const app = createApp(App)
app.use(VuePersianDatetimePicker, {
    name: 'custom-date-picker',
    props: {
        inputFormat: 'YYYY-MM-DD HH:mm',
        format: 'jYYYY-jMM-jDD HH:mm',
        editable: false,
        inputClass: 'form-control my-custom-class-name',
        placeholder: 'Please select a date',
        altFormat: 'YYYY-MM-DD HH:mm',
        color: '#00acc1',
        autoSubmit: false,
        //...  
        //... And whatever you want to set as default 
        //... 
    }
});
```
Then use in component
```html
<custom-date-picker v-model="date"></custom-date-picker>
```

### [Click to see prev full documentation and demo](https://talkhabi.github.io/vue-persian-datetime-picker)

## Built With
* [Vue.js](https://vuejs.org/) - The Progressive JavaScript Framework.
* [Moment.js](https://momentjs.com/) - Parse, validate, manipulate, and display dates and times in JavaScript.
* [moment-jalaali](https://github.com/jalaali/moment-jalaali) - A Jalaali (Jalali, Persian, Khorshidi, Shamsi) calendar system plugin for moment.js.


## License

This project is licensed under the MIT License


## Change log

### 1.0.1 (2021-03-16)
 