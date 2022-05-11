# Study-Log

1. 两种数据类型：
  a. 基本数据类型（byte, short, int, long, double, float, boolean, char）
      变量名指向具体的数值
  b. 引用数据类型（class, Interface, )
      变量名指向此object的地址
      
2. .equals() 和 == 的使用情景：
    a. 当数据类型为基本类型时， 可以用==
    b. 当数据类型为引用数据类型时，用.equals()
    
3. .equals()的原理：
    将此变量下的所有data和另一比较对象的所有data一一比较
    
4. 字符串常量池
     public static void main(String[] args){
        String str = "Hello World";
        String str1 = "Hello World";
        // 字符串常量池
        System.out.println (str==str1);// false

        String str2 = new String ("Hello World");
        System.out.println (str==str2);// false

        int i = 200;
        Integer j = 200;
        Integer j1 = 200;
        System.out.println (i==j);// true
        System.out.println (j==j1);// false
    }
