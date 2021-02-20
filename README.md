# vue-skelett

Simple skeleton builder to show skeleton view while loading the page.

---

![Sample loader card](https://media.giphy.com/media/RoU6BrMT316gTLh5f1/giphy.gif)

---

# Introduction

`vue-skelett` provides a skeleton view to show in place while the web page is loading. Currently it only supports `pulse` effect. It aims to provide maximum flexibility to create looks.

## Sample Code

> 🚨 [vue-skelett-sample](https://gist.github.com/tinas/47b507f7c796377c81804692a1b72c4f)

## Installing

```
$ npm install vue-skelett
```

# Usage
You can register the component globally, or use it in a particular component.

**To register in your `main.js`**
```javascript
import Vue from 'vue';
// Import the component
import VueSkelett from 'vue-skelett';

// Register the component globally
Vue.component('vue-skelett', VueSkelett);
```

**To register in your component**
```vue
<script>
import VueSkelett from 'vue-skelett';

export default {
  components: { VueSkelett },
};
</script>
```

**Using `vue-skelett` in your `.vue` file**

```vue
<template>
  <div class="skeleton-card">
    <vue-skelett
      type="circle"
      size="100"
    />
   <vue-skelett
      width="100%" //sets its width in percent
      height="20" //sets its width in px
      radius="10"
    />
  </div>
</template>
```


# API

### Props

|Prop|Type|Default|Options|Description|
|---|---|---|---|---|
|type|string|'flat'|circle, flat|This is the type of loader. It could be a `circle` or `flat`|
|width|number, string||%|This is the width of the shape and can be a number or a string. If the stage `size` is set, this property is overridden. Applies the percentage type if the `%` sign is appended to the end of the entered value. The default unit is `px`|
|height|number, string||%|This is the height of the shape and can be a number or a string. If the stage `size` is set, this property is overridden. Applies the percentage type if the `%` sign is appended to the end of the entered value. The default unit is `px`|
|size|number, string||%|This is used to give the loader the same width and height. The property overrides the preset width and height. Applies the percentage type if the `%` sign is appended to the end of the entered value. The default unit is `px`|
|radius|number, string|0|%|This is used to determine the loader's boundary radius. Applies the percentage type if the `%` sign is appended to the end of the entered value. The default unit is `px`|


## 🔑 License

MIT © [Ahmet Tınastepe](https://github.com/tinas)

> See [LICENSE](LICENSE) for details.