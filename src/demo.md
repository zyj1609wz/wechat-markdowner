## 微信公众号格式化工具

GitHub 地址：[https://github.com/ironmaxtory/wechat-markdowner](https://github.com/ironmaxtory/wechat-markdowner)

> 使用微信公众号编辑器有一个十分头疼的问题——粘贴出来的代码，格式错乱，而且特别丑。这块编辑器能够解决这个问题。

### Changelog

- 适配 Android
- 支持代码不转行，横向滚动条
- 支持页面主题样式配置

### 代码示例
`html`代码
```html
<h1 class="title">标题</h1>
```

---

`css`代码：
```css
.title {
    color: #000000;
    font-size: 20px;
}
```

---

`js`代码：
```javascript
var OnlineMarkdown = {
  init: function() {
    var self = this;
    self.load().then(function() {
      self.start()
    }).fail(function(){
      self.start();
    });
  },
  start: function() {
    this.updateOutput();
  },
  load: function() {
    return $.ajax({
      type: 'GET',
      url: params.path || './demo.md',
      dateType: 'text',
      timeout: 2000
    }).then(function(data) {
      $('#input').val(data);
    });
  },
  updateOutput: function () {
    var val = this.converter.makeHtml($('#input').val());
    $('#output .wrapper').html(val);
    PR.prettyPrint();
  }
};

OnlineMarkdown.init();
```
---

`php`代码：

```php
echo 'hello,world'
```

### 表格示例

| 品类 | 个数 | 备注 |
|-----|-----|------|
| 苹果 | 1   | nice |
| 橘子 | 2   | job |

### 关于何大叔

<!-- ![微信公众号](http://cdn.ironmaxi.com/images/wechat/qrcode_300x300.png) -->
<p style="text-align:center;">
    <img style="width:200px;" src="http://cdn.ironmaxi.com/images/wechat/qrcode.png" alt="微信公众号"/>
</p>
---
