#Vue 基础
```html
<body>
    <div id="第一个应用">
        {{信息}}
    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var 应用 = new Vue({
            el:'#第一个应用',
            data:{
                信息:'Hello world!'
            },
        })
    </script>

</body>
```

