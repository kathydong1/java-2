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

正则表达式
    属于java.util.regex
    ^以什么开头
    $以什么结尾
    [0-9A-Za-z]数字大小写字母任意一个字符
    +一个或者多个
    ?一个或者没有
    {n}固定有N个
    {n,m}有n或者到m个
    .表示任意字符
    |或者
    \w 匹配单词字符    \W非单词
    \d 匹配数字        \D非数字
    \s 匹配空格        \S非空格
    

  顶级对象Object：
       JAVA得类最顶级的都是继承Object，Object内置一些常用方法，例如toString，我们现在用的stringbuilder等方法都是重写Object的toString方法，
       equal：是只比较内容，不比较对象的
       ==：比较对象
       八种基本类型是不能用面向对象的方法继承的，所有JAVA封装好了一些类用于包装基本类型到对象，成为包装类，
  八种包装类
     属于Java.lang包
      Interger intclass=new Interger(整形)
      Double douclass=new Double(双精度浮点数)
      Float floatclass=new Float(单精度浮点数)
      Character charclass=new Character(char字符)
      Short shortclass=new Short()
      Byte byteclass=new Byte()
      Boolean booclass=new Boolean()
      Long longclass=new Long()
 byte,short,char—> int —> long—> float —> double 
 
 
 日期操作：
    属于java.text.Date
    //获取到1970年零点零时到现在的英文时间
    Date d=new Date()
    //获取所有的毫秒数
    d.getTime()
    //将时间至回到初始值
    d.setTime(0);
    //Date与String的互转用法，这里需要用到SimpleDateFormat
     属于java.text.SimpleDateFormat;
     SimpleDateFormat formatter = new SimpleDateFormat("yyyy-MM-dd HH-mm-ss");
     String dateString = formatter.format(d);
     System.out.println(dateString);
     Date date = formatter.parse(dateString);
    
    
    由于Date类中将getYear(),getMonth()等获取年、月、日的方法都废弃了
    所以要借助于Calendar来获取年、月、日、周等比较常用的日期格式
   canlender类,该类不能被new
   String reg="yyyy-MM-dd HH-mm-ss"
   //获取到时间
   Canlender.getInstance()
   //canlender类转字符串
   Date cd=Canlender.format(reg)
   
   
   
   
   
   
   
   
   
   
   
   
   Java多线程
       进程：1个CPU只能运行一个进程，一个进程至少有一个线程
       线程声明周期
           start--->runnable---->running---->dead
       声明线程的两种方法
       //直接extends Thread然后实现run方法
       class A extends Thread{
          public void run{
	  }
        }
      //实现runnable接口，然后传入runnable参数
      class  R implements Runnable{
            public void run{
	    }
       }
       Thread  T=new Thread(R)
       
       
      //匿名多线程
      Thread T=new Thread(){
         public void run{
	 //运行代码
	 }
      }
      T.start()------>开启一个线程
      T.sleep(毫秒数)---类似定时器延迟该线程的running到runnable状态，结束后进入runnable状态
      T.getId()----->获取线程的唯一标识
      T.getName()----->获取线程的名字
      T.getPriority()----->获取线程的优先级    一般线程优先级是0-10，默认是优先级越高，系统分配的时间越多一些
      T.isAlive()------>返回布尔值，判断是否是在运行状态
      T.Deaom()------>返回布尔值，判断是否是守护进程    设置守护进程  T.setDeaom(),     当所有前台线程结束后，守护线程不管是否在运行，都默认结束
      
      
      
      线程安全问题：
        安全线程问题一般是由多个线程操作一个方法和一个变量时导致出现线程安全问题，
	Thread T=new Thread(){public void run{执行代码}}
	T.join()在另外i的线程中调用，用于当前线程执行完毕之后执行另外的线程，但是这种方法过于绝对，如果只是想一小段代码是要变成同步的时候，这种发发就是比较死板的，，
	synchronized关键字，是用来给方法加上锁子，当一个线程执行该方法的时候是要给当前方法加上锁，当执行完之后解锁
        synchronized(同一个object){   要变成同步的代码的    }
	Object对象上有自己的两个方法，wait和natil   必须用natil促发wait
	
	
	
      
		
    
 
     
    
       
