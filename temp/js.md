立即执行函数


[JavaScript中的立即执行函数表达式](http://weizhifeng.net/immediately-invoked-function-expression.html)

```
(function(){ 
    console.log("test");
})();
```

---


[定义并且立即执行JS匿名函数拾遗](http://www.cnblogs.com/walkerwang/archive/2011/06/30/2093923.html)


```
//最流行的写法

(function(){   
     alert("run!")   
})();   
   
/* !号可以有1~正无穷个，所以这一种就可以衍生无数种方式 */ 
!!!(function(){   
     alert("run!")   
})();   
   
(function(){   
     alert("run!")   
}).call();   
   
(function(){   
     alert("run!")   
}).apply();   
   
(function(){   
     alert("run!")   
}());   
   
void (function(){   
     alert("run!")   
})();   
   
~(function(){   
     alert("run!")   
})();   
   
~!(function(){   
     alert("run!")   
})();   
   
/* 这个最好玩 */ 
delete (function(){   
     alert("run!")   
})();   
   
+(function(){   
     alert("run!")   
})();   
   
-(function(){   
     alert("run!")   
})();   
   
setTimeout(function(){   
     alert("run");   
},0);   
   
/*自由变态组合，可以衍生出无数种方式*/ 
~+-!(function(){   
     alert("run!")   
})();
```