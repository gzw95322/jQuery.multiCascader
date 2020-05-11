# jQuery.multiCascader
Jquery 多选级联下拉（esmodule版）

> **注意：**基于es6实现，目前只在webpack打包后才能正常使用。

## 调用

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <link rel="stylesheet" href="./index.scss" />
    <script src="https://cdn.bootcss.com/jquery/1.8.3/jquery.min.js"></script>
    <script src="./index.js"></script>
  </head>
  <body>
    <div id="areaSelected"></div>
    <script>
      $(function () {
        var data = [
          {
            name: "全国",
            id: 2703,
            children: [],
          },
          {
            name: "宁夏",
            id: 19,
            children: [
              {
                name: "固原",
                id: 1662,
              },
              {
                name: "石嘴山",
                id: 1663,
              },
            ],
          },
        ];
        $("#areaSelected").multiCascader({
          data,
          placeholder: "请选择地区",
          inputName: "areaId",
          isTwoDimensionValue: true,
          callBack() {
            // console.log(val);
          },
        });
      });
    </script>
  </body>
</html>

```



## 参数

| 参数                | 类型     | 默认值                                    | 注释                                                         |
| ------------------- | -------- | ----------------------------------------- | ------------------------------------------------------------ |
| data                | Array    | []                                        | 元数据                                                       |
| value               | Array    | []                                        | 已选项                                                       |
| inputName           | String   | "mucaser"                                 | input 名称                                                   |
| valueKey            | String   | "id"                                      | value的key名字                                               |
| labelKey            | String   | "name"                                    | label的key名字                                               |
| showLeafLabel       | Boolean  | true                                      | 是否展示children                                             |
| childrenKey         | String   | "children"                                | children的key名字                                            |
| placeholder         | String   | "请输入"                                  | placeholder                                                  |
| isTwoDimensionValue | Boolean  | false                                     | 返回值方式，true返回`[<父节点value>, <子节点value>]`，false返回`[<子节点value>]` |
| show                | Boolean  | false                                     | 初始化后是否展示                                             |
| list                | Object   | {<br />height:300,<br />width: 200<br />} | 下拉菜单的高度和宽度                                         |
| callBack            | Function |                                           | 回调，返回已选值                                             |
