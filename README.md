# 数据类型，equals/== 区别，字符串常量池

### 两种数据类型：
    a. 基本数据类型（byte, short, int, long, double, float, boolean, char）
        变量名指向具体的数值
    b. 引用数据类型（class, Interface, ...)
        变量名指向此object的地址
      
### .equals() 和 == 的使用情景：
    a. 当数据类型为基本类型时， 可以用==
    b. 当数据类型为引用数据类型时，用.equals()
    
### .equals()的原理：
    将此变量下的所有data和另一比较对象的所有data一一比较
    
### 字符串常量池
     public static void main(String[] args){
        String str = "Hello World";
        String str1 = "Hello World";
        
        //创建字符串常量时，JVM会检查字符串常量池中是否存在这个字符串
        //若字符串常量池中存在该字符串，则直接返回引用实例；若不存在，先实例化该字符串
        System.out.println (str==str1);// false

        String str2 = new String ("Hello World");
        System.out.println (str==str2);// false
    }

### Integer和int的比较
     public static void main(String[] args){
        int i = 200;
        Integer j = 200;
        Integer j1 = 200;
        System.out.println (i==j);// true
        System.out.println (j==j1);// false
        //Integer包装类型的数值和int基本数据类型的数值进行比较时
        //会自动拆为int，然后进行比较，实际上就变为两个int类型的数值的比较
        
        //拆箱的范围[-128,127]
        //即在范围内 Integer和Integer用==比较 return true
        //在范围外 return false
        Integer j = -128;
        Integer j1 = -128;
        System.out.println (j==j1);// true
        
        Integer j = 127;
        Integer j1 = 127;
        System.out.println (j==j1);// true
        
        Integer j = 200;
        Integer j1 = 200;
        System.out.println (j==j1);// false
        
        //Integer i5 = 数值;时，会被翻译成Integer i5 = Integer.valueOf(数值);
        //Integer执行valueOf()方法时，会对-128到127之间的数进行缓存
        //Integer i = 127时，会将127进行缓存，下次再写Integer i2 = 127时，就会直接从缓存中取，就不会new一个新对象
    }


