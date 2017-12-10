# oppo

> 和闪一起写的oppo官网
> *讲解知识点如下：*
> 1.vue动态添加class，使用:class="{className:isBoolean}",当isBoolean为true添加上此class，为false则remove此class。
> 2.vue动态添加style，:style="{borderTop:'1px solid '+ color(color为一个变量) }"
> 3.vue父到子传递数据，使用props。props可以使用数组接受，也可以使用对象。
``` bash
   如<my-header :title='titles'/>
   在myHeather内部接收title，可以:
   props:{title:{
    type: Array,
    default: []
   }}
```
>4.vue子到父传递数据，可以使用$emit。比如将<mySlide/>组件的当前index传递给父组件Home
``` bash
    我们可以在mySlide身上定义一个自定义事件，比如叫updateWhite;
    <my-slide @updateWhite='handleUpdate'></my-slide>
    在slide组件内部，我们可以用$emit来触发updateWhite事件。
    在slide组件内：this.$emit('updateWhite',index)
```

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
