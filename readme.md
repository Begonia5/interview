//一
var a = 1;
(function(){
    console.log(a);
    var a = 2;
})();

/* undefined */

//二
function a(){
    return 1;
}
(function(){
    console.log(a());
    function a(){
        return 2;
    }
})();

/* 2 */

//三
var o = {
    a : 1,
    b : function(){
        setTimeout(function(){
            console.log(this.a);
        }, 0);
        console.log(2);
    }
};
o.b();

/* 
2 
undefined
*/

//四
把字符串'a=1&b=2&c=3'解析成 {a:1,b:2,c:3}

/*
var o = {};
'a=1&b=2&c=3'.split('&').map(function(i){
  var r = i.split('=');
  o[r[0]] = r[1];
});
*/

//五
实现一个add方法,使add(2)(3)()结果为5;
/*
       if (arguments.length){
         return add(num + x);
       } else {
         return num;
       }
*/
/*
function add(num){
    return function(x){
        return arguments.length ? add(num + x) : num;
    }
}
*/