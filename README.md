JAVA-API
   不可操作的字符串方法String
   String Str="字符串"
   Str.indexOf(a，b):返回指定字符在此字符串中第一次出现处的索引。通过下标找到该下表的字符
   Str.lastindexOf()：从字符最后位置开始查找到当
   Str.charAt(index)返回指定索引处的 char 值。
   Str.length()获取字符串的长度
   Str.valueOf()将其他类型的字符转换成字符串形式
   Str.substr(2，6)剪切字符串从下标2位置开始截切到5位置结束
   Str.concat(str2)链接字符串，拼接
   str.toLowerCase()变小写
   str.toUpCase()变大写
   Str.trim()去两边空格
   Str.toString()返回字符串本身
   Str.startsWith(String prefix)==》返回true和false
   Str.endsWith(String prefix)==》返回true和false
   Str.matches(正则表达式)===》返回true和false
   Str.replaceAll(正则表达式，替换的内容)
   Str.split(正则表达式, 范围)==》返回切换后的数组
   
   可操作的字符串方法StringBuilder,并且不产生新的未使用对象。
   StringBuilder sb=new StringBuilder(‘可变字符串’)
   sb.append()==>向最后一位追加
   sb.insert(2)==>向指定的位置追加
   sb.delect(起始位置，结束位置)==>删除从起始位置开始到结束位置的前一项的字段
   sb.replace(起始位置，结束为止，替换内容)==>替换指定的字段
   

String str = "字符串";编译器会使用该值创建一个 String 对象，且这个字符串不可变，修改字符串就是在常量池中新建一个对象
String str=new String("字符串")等价于上边的写法
