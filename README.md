# วิธีใช้

## ไฟล์ `main.js`
```javascript
...
import datetime from './datetime-helper.js';
...

// Version 2
import { Vue } from 'vue';
...
// Vue.prototype.[ชื่อ Property ]
Vue.prototype.$dt = datetime;


// Version 3
import { createApp } from 'vue';
import App from './App.vue';
...
const app = createApp(App);
// app.config.globalProperties.[ชื่อ Property ]
app.config.globalProperties.$dt = datetime;

app.use(router).mount('#app')
```

## ไฟล์ `App.vue`
```javascript
// Version 2
export default {
  mounted() {
    console.log(this.$dt.dateFormat("YYYY-MM-DD"));
    // Output: 2021-08-29
  },
}

// Version 3
export default {
  mounted() {
    console.log(this.$dt.dateFormat("YYYY-MM-DD"));
    // Output: 2021-08-29
  },
}
```
