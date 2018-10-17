# 字符串中某一字符出现几次
```
var str = 'qwertyuilo.,mnbvcsarrrrrrrrtyuiop;l,mhgfdqrtyuio;.cvxsrtyiuo';
    var json = {};
    //遍历str拆解其中的每一个字符将其某个字符的值及出现的个数拿出来作为json的kv
    for (var i = 0; i < str.length; i++) {
      //判断json中是否有当前str的值 
      if (!json[str.charAt(i)]) {
        //如果不存在 就将当前值添加到json中去
        json[str.charAt(i)] = 1;
      } else {
        //else的话就让数组中已有的当前值的index值++;
        json[str.charAt(i)]++;
      }
    }
      //存储出现次数最多的值和次数
      var number = '';
      var num=0;
      //遍历json  使用打擂算法统计需要的值
      for (var i in json) {
        //如果当前项大于下一项
        if (json[i]>num) {
          //就让当前值更改为出现最多次数的值
          num = json[i];
          number = i;
        }
      }
      //最终打印出现最多的值以及出现的次数
      alert('出现最多的值是'+number+'出现次数为'+num);
```