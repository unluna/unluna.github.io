---
title: JQuery源码分析————"传为佳话的fn"
date: 2019-08-08 20:19:32
tags: [JQ,源码]
categories: JQuery源码分析
---
## 上代码
    (function (window, undefined) {
        // 绕了一圈，就是为了把jQuery.fn上的方法暴露出去
        var jQuery = function (selector,context) {

        return new jQuery.fn.init(selector,context)
    };
    jQuery.fn=jQuery.prototype={
      init:function (selector,context) {
        
      }
    };
    jQuery.fn.init.prototype=jQuery.fn;

    })(window);

### jQuery和fn和init等来等去，其实就是为了把fn上的方法暴露出去
- 相当于jQuery.fn.init.prototype = jQuery.fn = jQuery.prototype
- 也就是jQuery.fn.init.prototype = jQuery.prototype
- 也就是jQuery.fn.init = jQuery

<font style="color:red">注意：</font>最后真正暴露的不是fn，是extend

### 另外
- jQuery.fn.extend({}) 给jq添加方法，做插件的时候用，挂载到jq的原型上
- 如果直接在jQuery.extend({})上添加方法，就是jQuery的属性了，不推荐

