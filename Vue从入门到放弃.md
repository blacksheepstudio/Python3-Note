## Vue 基础
### Vue 声明渲染
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
## v- 指令
```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8" />
</head>

<body>
  <div id="第一个应用">
    <p v-if="是否红色" style="color: red;">{{信息}}</p>
    <p v-else>{{信息}}</p>
    <p v-show="是否显示">{{第二条信息}}</p>
    <button v-on:click="langCn">调用langCn方法</button>
    <input v-model="信息">

  </div>

  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  <script>
    var 应用 = new Vue({
      el: "#第一个应用",
      data: {
        信息: "Hello world!",
        第二条信息: "我显示了！",
        是否红色: true,
        是否显示: true
      },
      methods: {
        langCn: function () {
          this.信息 = '你好，世界！'
        }
      }
    })
  </script>
</body>

</html>

```
