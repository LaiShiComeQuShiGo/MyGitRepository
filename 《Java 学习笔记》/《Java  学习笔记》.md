# 《Java  学习笔记》

## 第一阶段	  Java语言入门

### 编程基础

#### Java程序入门

#### 关键字

- **概念**：有特殊含义，被保留的，不能随意使用的字符。
- **特征**：
    1. 全部是小写
    2. 加强版记事本及其他工具，字体颜色发生改变
- 

#### 标识符

- **概念**：是指在程序中，我们自己定义的内容。例如：类的名字、方法的名字等等。

- **命名规则**：【硬性要求】

	1. 标识符包含：英文字母26个（区分大小写）、0-9数字、$（美元符号）和_（下划线）；
	2. 不能以数字开头；
	3. 不能是关键字；

- **命名规范**：【软性建议】

	1. 类名规范：首字母大写，后面每个单词首字母大写（大驼峰）；

	```java
	  public class HelloWorld{}//类名称：HelloWorld
	```

	2. 变量名规范：首字母小写，后面每个单词首字母大写（小驼峰）;

	```java
	  int numClass;//变量名：numClass
	```

	3. 方法名规范：同变量名规范一样；

	```java
	  public static void methodTest（）{}//方法名：methodTest
	```

	4. 见名知意；

- 

#### 常量

- **概念**：在程序运行期间，固定不变的。
- **分类**：
	1. 字符串常量：凡是用英文**双引号**引起来的部分。//"hello"
	2. 整数常量：直接写上的数字，没有小数点。// 100
	3. 浮点常量：直接写上的数字，有小数点。// 1.0
	4. 字符常量：凡是用英文**单引号**引起来的**单个字符**。// 'A'
		【注意】单引号里有且仅有一个字符，多了或者没有都不可以。
	5. 布尔常量：只有两种取值（true、false）。
	6. 空常量：null。代表没数据
- 

#### 变量

- **概念**：程序运行期间，内容发生改变的量。

- **格式**：

	- 数据类型 变量名称 = 数据值；

	```java
	  int num = 10;
	```

- **注意事项**：

1. 如果创建多个变量，变量之间的名称不可重复。（数据类型  变量名称    就是创建了一个变量，栈中开辟空间）

	```java
	int num = 10;//创建了一个变量，名叫num。没毛病！！！
	int num = 20;//又创建了一个变量，也叫num。错误
	```

2. 对于float和long类型来说，字母后缀F和L不要丢

	```java
	long num = 22000000000;//错误提示：过大的整数：2200000000
	```

3. 如果使用byte和short类型的变量，右侧的数据值不能超过左边类型的范围

	```java
	byte num = 1000;//错误提示：不兼容的类型：从int到byte可能会有损失
	```

4. 变量使用前，一定要先赋值

	```java
	int num ;
	System.out.println(num);//错误提示：可能尚未初始化变量num
	```

5. 变量使用不能超过作用域的范围
	【作用域】：从定义变量的一行开始，一直到直接所属的大括号结束为止。

	```java
	{
	    int num = 10; 
	}
	System.out.println(num);//错误：需要<标识符>
	```

6. 可以通过一个语句（一个分号代表一个语句）来创建多个变量，多个变量的数据类型一致。

	```java
	int a,b;
	a = 10;
	b = 20;
	//或者
	int c =10 ,d = 20;
	```

	

#### 数据类型

- **基本数据类型**：整数、浮点数、字符、布尔。（四类八种）

	| 数据类型     | 关键字         | 内存占用(字节) | 取值范围          |
	| ------------ | -------------- | -------------- | ----------------- |
	| 字节型       | byte           | 1Byte          | -128~127          |
	| 短整型       | short          | 2Byte          | -3万~3万          |
	| 整型         | int (默认)     | 4Byte          | -21亿~21亿        |
	| 长整型       | long           | 8Byte          | -900亿亿~900亿亿  |
	| 单精度浮点数 | float          | 4Byte          | 1.4E-45~1.4E+38   |
	| 双精度浮点数 | double（默认） | 8Byte          | 4.9E-324~1.7E+308 |
	| 字符型       | char           | 2Byte          | 0~6万             |
	| 布尔类型     | boolean        | 1Byte          | true、false       |

- **引用数据类型**：类、数组、接口。

- 

#### 数据类型转换

- **概念**：当数据类不一样的时候，将会发生数据类型转换

- **自动转换**（隐式）

	1. 特点：代码不需要进行特殊处理，自动完成。
	2. 规则：数据范围从小到大

- **强制类型转换**（显式）

	1. 特点：代码需要进行特殊处理，不能自动完成。

	2. 规则：数据范围从大到小

	3. 格式：范围小的类型  范围小的变量名 = （范围小的类型）原来范围大的数据；

		```java
		int num = (int)100L;
		System.out.println(num);//100
		```

		- 【**注意事项**】：

			1. 强制类型转换一般不推荐，因为有可能发生精度损失、数据溢出。

				```java
				//long ————> int ,强制类型转换
				int num = (int) 60000000L;
				System.out.println(num);//1705032704发生数据溢出
				//double————> int
				int num1 = (int)3.14;
				System.out.println(num1);//3，这不是四舍五入，而是精度损失，把所有小数去掉。
				```

				

			2. byte/short/char这三种类型在运算的时候，都会被首先提升为int类型，然后再计算。

		- 

- 

#### 运算符

#### 流程控制

#### 方法

#### 数组

- **概念**：是一种容器，可以存放多个数据值。

- **特点**：

	1. 数组是引用数据类型
	2. 数组当中多个数据值，类型必须统一
	3. 数组的长度在运行期间不可改变

- **格式**

	- 初始化格式：在内存当中创建一个数组，并向其中赋予一些默认值

		1. 动态初始化（指定长度）

			- 格式:  数据类型 []  数组名称 = new 数据类型[数组长度]；

				```java
				int[] array = new int[3];//长度为3，int类型数组
				```

			- 

		2. 静态初始化(指定内容)

			- 标准格式：数据类型[]  数组名称 = new  数据类型[]{元素1,元素2,元素3,....}；

				```java
				String[] array = new String[]{"a","b","c"};//字符串类型数组，长度根据内容确定
				```

			- 省略格式：数据类型[]  数组名称 = {元素1,元素2,元素3,........}；

				```java
				String[] array = {"a","b","c"};//省略 new String[]
				```

			- 

	- **使用**

		1. 获取

			- 格式：数组名称[索引值]；
			- 【注意】
				1. 索引值：就是一个int数值，代表数组元素的位置编号
				2. 索引是从“0”号开始，一直到“数组长度 - 1”为止结束
				3. 直接打印数组，得到的是数组对应的 内存哈希值
			- 

		2. 赋值

			- 格式：数组名称[索引值] = 赋值内容；

			- 【扩展】

				<> 使用动态初始化时，数组元素有一个默认值，规则如下

				1. int类型，默认值是：0
				2. float/double类型，默认值是：0.0
				3. char类型，默认值是：'\u0000'（十六进制）
				4. boolean类型，默认值是：false
				5. 引用类型，默认值是null

				<> 使用静态初始化时，分两步：

				1. 系统先给默认值
				2. 再把大括号里的元素赋值给默认值

			- 

		3. 长度

		4. 

	- 

- 

#### IDEA开发工具 

### 面向对象

#### 类和对象

- ##### 普通类

- ##### 内部类

	- **概念**

		- 一个事物内部包含另一个事物，那么就是一个类包含另一个类
		- 【例如】身体和心脏的关系；汽车和发动机的关系

	- **分类**

		- 成员内部类
		- 局部内部类（包含匿名内部类）

	- **成员内部类**

		- **格式**

			````java
			public class 外部类名称 {
			      public class 内部类名称{
			          // 内部类方法体
			      }
			      // 外部类其他方法体
			}
			````

			````java
			 public class Body{
			        public class Heart{
			            public void method(){
			                sout("内部类方法执行");
			            }
			        }
			        public void methodBody(){
			            sout("外部类方法执行");
			            //通过此方法间接调用内部类方法
			            new Heart().method();
			        }
			  }
			````

		- **内部类访问外部类内容的方式**

			1. 与外部类成员方法一样，随意访问

			2. 当内部类的变量与外部类成员变量重名时

				- 访问外部类成员变量格式：**外部类.this.成员变量名称**

					````java
					public class Outer{
					    int num = 10;
					    public class Inner{
					        int num = 20;
					        public void method(){
					            int num = 30;
					            System.out.println(num);//30;局部变量，采用就近原则
					            System.out.println(this.num);//20;内部类成员变量；
					            System.out.println(Outer.this.num);//10;外部类成员变量；
					        }
					    }
					}
					````

		- **外部类访问内部类内容的方式**

			1. 通过外部类成员方法间接访问

				````java
				//通过创建外部类对象，调用外部类成员方法，间接访问内部类
				Body body = new Body();
				body.methodBody();
				-------------------
				 //这是外部类成员方法
				    public void method(){
				    //通过内部类对象调用内部类成员方法
				    new Heart().method();//此method()方法是内部类中的，与外部类的成员方法重名。
				}
				````

			2. 直接使用内部类对象，进行访问

				【公式】**外部类名称.内部类名称	对象名 = new 外部类名称().new 内部类名称 ();**

				````java
				Body.Heart obj = new Body().new Heart();
				obj.method();
				````

		- 

	- 局部内部类

		- 概念

			1. 如果一个类定义在一个方法内部，这个类就是局部内部类
			2. “局部”：只能该方法使用，出了该方法外面就不能用了

		- 格式

			````java
			修饰符 class 外部类名称{
			    修饰符 返回值类型 方法名称（参数列表）{
			        class 内部类名称{
			            //方法体
			        }
			    }
			}
			````

		- 使用方式

			1. 外部类对象调用含有局部内部类的方法

			2. 在含有内部类的方法中创建内部类对象，再调用里面的内容

				````java
				Outer obj = new Outer();
				obj.method();
				-------------------
				public void method(){
				    class Inner{
				        public void methodInner(){
				            System.out.println("这是局部内部类的成员方法");
				        }
				    }
				    Inner inner = new Inner();
				    inner.methodInner();
				}
				````

				

		- 

	- 匿名内部类

		- 【**功能**】如果接口的实现类 or父类的子类，只需使用唯一的一次，那么该实现类or子类可以省略该类的定义，而改为匿名内部类。

		- 格式

			````java
			接口名称 对象名 = new 接口名称（）{
			    //覆盖重写所有抽象方法
			};//这个分号不能丢
			````

			【解析】对格式“new 接口名称(){...};”进行解析

			1. new 代表创建对象的动作；
			2. 接口名称就是匿名内部类要实现的那个接口
			3. {...}这才是匿名内部类的内容

		- 【注意事项】

		- 

	- 

- ##### 

- ##### 

#### 封装

#### 继承

- **概念**

- **【功能】**继承主要解决的 问题是：**共性抽取**

- **特点**：

	1. java语言是单继承的。（一个类的直接父类有且仅有一个）
	2. java语言可以多级继承。（我有一个父亲，我父亲还有一个父亲，也就是爷爷）
	3. java语言中一个父类可以拥有多个子类。（有很多兄弟姐妹）

- **格式**

	1. 定义父类的格式：与普通类的定义一样 

		```java
		public class 类名称{
			//....
		}
		```

	2. 定义子类的格式：使用extends关键字

		```java
		public class 子类名称 extends 父类名称 {
		    //....
		}
		```

	3. 

- **重名问题**

	- 成员变量重名：（访问两种方式）

		1. 直接通过子类对象访问

			- 【规则】：等号左边是谁，优先用谁

				```java
				Zi zi = new Zi();
				System.out.println(zi.num);//优先使用子类的重名num,没有则向父类中找，都没有编译报错;
				```

		2. 间接通过成员方法访问

			- 【规则】：方法属于谁，就优先用谁的num

				```java
				public void methodZi(){System.out.println(num);}//子类方法中访问重名成员变量
				public void methodFu(){System.out.println(num);}//父类方法中访问重名成员变量
				-----------------------------------------
				zi.methodZi();//该方法属于子类的方法，所以优先使用子类的成员变量num,没有则用父类的中的num；
				zi.methodFu();//该方法属于父类的方法，所以优先使用父类的成员变量num，没有则会编译报错，不会向子类中找；
				```

	- 成员方法重名

		- 【规则】：new() 的是谁就优先用谁，没有则向上找

			```java
			Zi zi = new Zi();
			
			zi.method();//method方法，子类父类中都有，new的是子类对象，所有优先调用子类中的方法。
			```

	- 子类方法中三种重名访问格式：

		1. 局部变量：直接访问

		2. 本类中的成员变量：this.成员变量名称

		3. 父类中的成员变量：super.成员变量名称

			```java
			int num = 20;
			pulic void method(){
			    int num =30;
			    System.out.println(num);//30,局部变量；
			    System.out.println(this.num);//20,本类中的成员变量；
			    System.out.println(super.num);//10,父类中的成员变量；
			```

	- 

- **方法的覆盖重写（override）**

	- **概念**：在继承关系中，父子类中的方法名称、参数列表也一样。

	- 格式：

		```java
		@Override  //写在子类中要覆盖重写的方法前面，用来检测是否有效正确覆盖重写。不写也可以，推荐写
		public void method(){} //【方法名称】【参数列表】与父类一样
		```

	- 【返回值类型】

		- 【规则】：可以不一样，但是必须【小于等于】父类方法的返回值

	- 【权限修饰符】

		- 【规则】：可以不一样，但是必须【大于等于】父类方法的权限修饰符

	- 【区分】

		- 重写（override）:方法名称【一样】，参数列表【也一样】
		- 重载（overlode）:方法名称【一样】，参数列表【不一样】

	- 

- **构造方法**

	- 特点

		1. 子类构造方法中有一个默认隐含的super()调用

			```java
			public Zi(){
			    super();//隐含着一个无参构造方法；默认赠送
			}
			//创建子类对象时，先调用父类构造，然后执行子类构造方法
			```

		2. 子类构造可以通过super关键字调用父类重载构造方法

		3. super的父类构造方法调用，必须是子类构造方法的第一个语句

			```java
			public Zi(){
			    super();//此处为第一个语句，以分号为界限；
			    System.out.println();//此处为第二个语句；
			}
			```

		4. 

	- 

- **this 和 super 关键字的三种用法**

	- 【**功能**】：这两个关键字是用来解决：**变量重名问题**

	- this关键字的用法

		1. 在本类**成员方法**中，访问本类中的**成员变量**。

			```java
			int num =10;
			public void method(){
			    int num = 20;
			    System.out.println(num);//20;局部变量；
			    System.out.println(this.num);//10;访问本类中的成员变量num;
			}
			```

		2. 在本类**成员方法**中，访问本类中的另一个**成员方法**。

			```java
			public void methodA(){
			    methodB();//这是第一种，调用methodB的方法；
			    this.methodB();//这是第二种，强调是本类中的成员方法，而不是父类的
			}
			public void methodB(){
			    
			}
			```

		3. 在本类**构造方法**中，访问本类中的另一个**构造方法**。

			```java
			public Zi(){
			    //super();//这一行不再赠送；
			    this(10);//本类的无参构造，调用本类的有参构造；
			    this(10,20);//错误写法，不能有两个调用与this(10)冲突；
			}
			public Zi(int n){
			    this(10，20);//调用两个参数的构造方法；
			}
			pulic Zi(int n ,int m){
			    super();//调用父类构造方法；
			}
			```

			- 【注意】

				A:    this(....)调用必须是构造方法中的第一个语句，且是唯一的一个。

				B:    super和this 两种构造，不能同时使用。

	- super关键字的用法

		1. 在子类成员方法中，访问父类类中的成员变量。

			```java
			int num = 10;
			public void method(){
			    super.num;//访问父类中的成员变量；
			}
			```

		2. 在子类成员方法中，访问父类中的另一个成员方法。

			```java
			public void method(){
			    super.method();//访问父类中的成员方法method;
			}
			```

		3. 在子类构造方法中，访问父类中的构造方法

			```java
			public Zi(){
			   super();//子类构造方法中访问父类构造方法，不写会默认赠送；
			}
			```

		4. 

	- 

- 

#### 多态

- **概念**：一个对象拥有多种形态，这就是对象的多态性。

	- 代码当中体现多态性，就是：**父类引用指向子类对象**
	- 【例如】：小明是一名学生（学生形态），同时也是人类（人类形态）

- **格式**

	````java
	父类名称  对象名 = new 子类对象名称();
	````

	````java
	接口名称  对象名 = new 实现类名称();
	````

- **重名变量**

	- 与继承中一样

- **向上转型**

- **向下转型**

	- instanceof关键字

		- 【**功能**】判断前面的对象能不能当作后面的实例，这将得到一个布尔值的结果

		- 格式：**对象名   instanceof  类名称**

			````java
			if(animal instanceof Cat){
			    Cat cat = (Cat)animal;
			}
			````

		- 

	- 

	- 

- 

- 

#### 抽象类

#### 接口

- ##### 概念

- ##### **格式**：

	````java
	public interface 接口名称 {
	    //接口内容
	}
	````

	【备注】：关键字由class换成interface后，编译生成的字节码文件仍然是.class。

- **接口中的内容**

	- 如果是java7，接口中的内容包含：

		1. **常量**

			- 定义格式

				````java
				public static final 数据类型 常量名称 = 数据值；
				````

				【备注】：一旦使用final关键字，说明不可改变

			- 【注意事项】

				1. 接口当中的常量，可以选择性省略public、static、final

				2. 接口当中的常量， 必须进行赋值，否则编译报错

				3. 接口当中的 常量，（推荐命名规则）全部使用大写字母，使用下划线进行分隔

					````java
					public static final int NUM_OF_CLASS = 10;
					````

		2. **抽象方法**

			- 定义格式

				````java
				public abstract 返回值类型 方法名称（参数列表）；
				````

			- 【注意事项】

				1. 接口当中抽象方法，修饰符必须是两个固定的关键字：public、abstract

				2. 两个关键字可以选择性地省略。

					````java
					public abstract void method();//完整写法
					public void method();//省略abstract
					abstract void method();//省略public
					void method();//两个都省略
					````

				3. 抽象方法没有方法体大括号，小括号后直接加分号。

			- 

	- 如果是Java8，接口中的内容额外包含：

		3. **默认方法**

			- 【**功能**】：解决接口升级问题
			- 定义格式
			- 【注意事项】
				1. 接口中的默认方法，修饰符也是两个固定的关键字：public、default
				2. 两个关键字可以省略public，但是default不能省略。
			- 

		4. **静态方法**

			- 定义格式

				````java
				public static 返回值类型 方法名称（参数列表）{方法体}
				````

			- 【注意事项】

				1. 两个固定关键字（public、static），可以省略public，不能省略static；
				2. 不能通过接口实现类的对象来调用接口中的静态方法
				3. 【正确用法】：**接口名称.静态方法();**

			- 

	- 如果是Java9，接口中的内容还额外包含：

		5. **私有方法**

			- 【**功能**】

				1. 普通私有方法：解决多个默认方法之间重复代码问题
				2. 静态私有方法：解决多个静态方法之间重复代码问题

			- 定义格式

				1. 普通私有方法

					````java
					private 返回值类型 方法名称（参数列表）{方法体}
					````

					【注意】：只有一个关键字private，不能省略。

				2. 静态私有方法

					````java
					private static 返回值类型 方法名称（参数列表）{方法体}
					````

					【注意】：两个关键字都不能省略

			- 

	- 

- ##### 接口的使用

	- 使用步骤

		1. 创建“实现类”来“实现”该接口

			- 格式

				````java
				public class 实现类名称 implements  接口名称{方法体}
				````

			- 【建议】实现类名称命名规则：**接口名称+Impl**

		2. 覆盖重写接口中所有的抽方法

			- 格式

				````java
				//去掉abstract,加上方法体大括号
				````

		3. 创建实现类对象，进行使用

	- 【注意事项】：

		1. 接口中是没有静态代码块和构造方法的

		2. 一个类的直接父类有且只有一个，但是可以同时实现多个接口

			````java
			  public class MyInterfaceImpl implements MyInterfaceA,MyInterfaceB{
			      //覆盖重写所有抽象方法
			  }
			````

		3. 如果实现类所实现的多个接口中，存在重复（即：重名）抽象方法，只需覆盖重写一次即可。

		4. 如果实现类所实现的多个接口中，存在重复的默认方法，那么实现类一定要对冲突的默认方法进行覆盖重写。

		5. 如果实现类的父类当中的方法，与实现类所实现接口中的抽象方法重名，那么，实现类当中不必覆盖重写此抽象方法。

		6. 如果实现类的的父类当中的方法，与实现类所实现接口中的默认方法重名，那么，优先使用父类当中的方法。

		7. 如果实现类没有全部覆盖重写接口当中的抽象方法，那么，该实现类必须是抽象类。

	- 

- 接口之间的关系

	- 接口、类之间的关系

		1. 类与类之间是**单继承**的，直接父类只有一个。

		2. 类与接口之间是**多实现**的，一个类可以实现多个接口。

		3. 接口与接口之间是**多继承**的。

			````java
			public interface MyInterface extends MyInterfaceA,MyInterfaceB{
			    //。。。。
			}
			````

	- 【注意事项】

		1. 多个父类接口当中的抽象方法重复，没关系。
		2. 多个父类接口当中的默认方法重复，子接口必须覆盖重写默认方法

- 

- 

#### 权限修饰符

- 四种权限修饰符

	- public > protected > (default) > private （范围从大到小）

		| 使用范围（可不可以访问） | public | portected | (default) | private |
		| :----------------------- | :----: | :-------: | :-------: | :-----: |
		| 同一个类                 |  Yes   |    Yes    |    Yes    |   Yes   |
		| 同一个包                 |  Yes   |    Yes    |    Yes    |         |
		| 不同包子类               |  Yes   |    Yes    |           |         |
		| 不同包非子类             |  Yes   |           |           |         |

	- 【注意】default 不是关键字，而是省略不写

		```java
		public class My {
		    int num = 10;
		    public void myMethod(){
		        System.out.println(num);//同一个类中可以访问num;
		    }
		}
		```

		```java
		public class neighbor {
		    public void neighborMethod(){
		        System.out.println(new My().num);//同一包下，访问num,至少是（defaut）
		    }
		}
		```

		

	- 

- 定义一个类时，权限修饰符规则

	1. 外部类：public 或者（default）
	2.  成员内部类：public、protected、(default)、private
	3.  局部内部类：什么都不写

- 

- 

#### static

- 【**功能**】：数据共享，该内容**属于类**，该类所有对象，共享同一份数据

- **使用**

	- 如果没有static关键字，必须先创建对象，通过对象来使用

	- 如果有了static关键字，那么不需要创建对象，通过类名也可以使用

		````java
		public class MyClass{
		    int num = 10;
		    static int numSta = 20;
		    public static void method(){}//该方法是静态方法
		}
		---------------------------------------
		MyClass obj = new MyClass();
		sout(obj.num);//正确，必须这样
		sout(obj.numSta);//正确，但是不推荐
		sout(MyClass.numSta);//正确，推荐
		obj.method();//正确，但是不推荐
		MyClass.method();//正确，推荐 类名称.静态方法();
		````

	- 无论是成员变量，还是成员方法，如果有了static，都【推荐】使用类名调用

		- 格式：静态变量 ：  **类名称.静态变量；**
		- 格式：静态方法：**类名称.静态方法();**

	- 【注意】**静态不能直接访问非静态**

		````java
		public class MyClass{
		    int num = 10;
		    static int numSta = 20;
		    public void method(){//这是个成员方法
		        sout(num);//正确
		        sout(numSta)//正确
		    }
		    public static void methodStatic(){//这是个静态方法
		        sout(num);//错误，静态访问非静态
		        sout(numSta);//正确，静态访问静态
		    }
		}
		````

	- 

- **静态代码块**

- 

- 

#### Scanner

- **功能**：实现键盘输入数据到程序当中

- **使用步骤**

	1. 导包：**import   包路径 . 类名称**；

		```java
		import java.util.Scanner;
		```

		- 如果使用的目标类和当前类位于同一包下，则省略导包语句
		- 只有java.lang包下的内容，不需要导包，其他的包都需要import语句

	2. 创建：**类名称 对象名 = new 类名称();**

		```java
		 	Scanner sc = new Scanner(System.in);
		//System.in 代表从键盘输入
		```

	3. 使用：**对象名.方法名();**

		```java
		//获取键盘输入的int数值
		int num = sc.nextInt();
		//获取键盘输入的一个字符串
		String str = sc.next();//不是nextString()
		```

- 

- 

#### Random

- **功能**：用来生成随机数字

- **使用步骤**

	1. 导包

		```java
		import java.util.Random;
		```

	2. 创建

		```java
		Random rd = new Random();
		```

	3. 使用

		```java
		//1.获取一个随机int数字，范围（-21亿-21亿）
		int num = rd.nextInt();
		//2.获取一个指定范围的数字
		//参数代表了范围，左闭右开区间，[0,3),即0，1，2
		int num = rd.nextInt(3);
		//3.获取一个[1,3]的范围
		int num = rd.nextInt(3)+1;
		```

-  

- 

#### ArrayList

- **功能**：数组长度不可以改变，但ArrayList的长度是随意发生改变的

- **使用步骤**

	1. 导包

		```java
		import java.util.ArrayList;
		```

	2. 创建

		- 格式：**ArrayList<E>  集合名称  =  new  ArrayList<>();**

			```java
			ArrayList<String> list = new ArrayList<>();
			```

		- 尖括号<E> 代表泛型，泛型只能是引用类型，不能是基本类型

		- 泛型：指集合当中所有的元素，都统一一个类型

	3. 使用

		- 向集合中**添加**元素

			```java
			//public boolean add(E a):参数的类型和泛型一样
			list.add("hello");
			System.out.println(list);//[hello]
			```

		- 从集合中**获取**元素

			```java
			//public E get(int index):参数是索引位置，返回值类型是对应位置上的元素
			list.get(1);
			```

		- 从集合当中**删除**元素

			```java
			//public E remove(int index):参数是索引编号，返回值类型是被删除的元素
			list.remove(1);
			```

		- 获取集合的**长度**

			```java
			//public int size():返回值是集合当中元素的个数
			list.size():
			```

		- 【注意】对于ArrayList集合来说，直接打印所得到的不是地址值，而是集合中的内容。

			````java
			System.out.println(list);//[hello]
			````

		- 

- **Arraylist集合存储基本类型**

	- 如果使用ArrayList存储基本类型，必须使用它们的包装类

		| 基本数据类型 |      包装类       |
		| :----------: | :---------------: |
		|     byte     |       Byte        |
		|    short     |       Short       |
		|     int      |  Integer【特殊】  |
		|     long     |       Long        |
		|    float     |       Float       |
		|    double    |       Doule       |
		|     char     | Character【特殊】 |
		|   boolean    |      Boolean      |

	- 使用方式

		````java
		//1. 创建集合
		ArrayList<Integer> list = new ArrayList<>();
		//2. 向集合当中添加int类型数据
		list.add(100);
		````

		

- 

- 

#### String

- ##### 概念

	- java.lang.String代表字符串
	- 程序当中所有双引号字符串，都是string类的对象，（没有new也是）。
	- 字符串的特点
		1. 字符串的内容永不变。
		2. 字符串是 可以共享使用的，（正是因为字符串内容永不变）
		3. 字符串效果上相当于char[]字符数组，但是底层原理是byte[]字节数组

- ##### 创建方式（3+1种）

	- 三种构造方法

		1. public String();//创建一个空的字符串，不含任何内容。

			```java
			//空参构造，小括号留空，表示字符串什么内容都没有
			String str1= new String();
			```

		2. public String(char[] array);//根据字符数组内容，来创建字符串。

			```java
			char[] charArray = {'a','b','c'};
			String str2 = new String(charArray);
			```

		3. public String(byte[] array);//根据字节数组内容，来创建字符串。

			```java
			byte[] byteArray = {97,98,99};
			String str3 = new String(byteArray);
			```

	- 一种直接创建

		````java
		String str4 = "hello";
		````

- ##### 字符串常量池

	- 程序当中直接写上的双引号字符串，就在字符串常量池中。

		![](E:\Java系列\《Java 学习笔记》\常量池内存图.jpg)

	- 

- ##### 字符串的比较

	- ==的使用

		1. 对于基本类型来说，==是进行数值的比较。
		2. 对于引用类型来说，== 是进行地址值的比较。

	- 引用类型内容的比较方法

		1. 使用equals()方法

			```java
			public boolean equals(Object obj){}
			//1.参数是任意对象
			//2.只有参数是字符串并且内容相同时，才返回true
			```

			```java
			String str1 = "abc";
			String str2 = "abc";
			char[] array = {'a','b','c'};
			String str3 = new String(array);
			
			System.out.println(str1.equals(str2));//true
			System.out.println(str1.equals(str3));//true
			System.out.println(str1.equals("hello"));//false
			```

			- 【注意事项】

				1. equals()方法具有对称性，也就是a.equals(b)和b.equals(a)效果一样。

				2. 如果比较双方一个常量和一个变量，推荐把常量字符串写在前面

					```java
					String str = "abc";
					System.out.println("abc".equals(str));//推荐
					System.out.println(str.equals("abc"));//不推荐
					//当str = null;时 str.equals("abc");会抛出异常
					```

		2. 使用equalsIgnoreCase(String string)方法

			```java
			public boolean equalsIgnoreCase(String string){}
			//1.参数类型是String
			//2.比较时忽略大小写
			```

			```java
			String str = "Hello";
			System.out.println("hello".equals(str));//false,严格区分大小写
			System.out.println("hello".equalsIgnoreCase(str));//ture，忽略大小写
			```

		3. 

	- 

	- 

- ##### 字符串的获取

	- 获取字符串的长度

		```java
		public int length(){}
		//获取字符串中字符的个数，返回字符串的长度
		```

	- 拼接字符串

		```java
		public String concat(){}
		//1.将当前字符串与参数字符串拼接，返回【新字符串】
		//2.与加号“+”效果一样
		String str1 = "Hello";
		String str2 = "World";
		String str3 = str1.concat(str2);//等效于：String str3 = str1 + str2;
		
		System.out.println(str1);//Hello
		System.out.println(str2);//World
		System.out.println(str3);//HelloWorld
		```

	- 获取指定索引位置的单个字符

		```java
		public char charAt(int index){}
		//获取指定位置的单个字符，索引从0开始
		char ch = str1.charAt(4);
		System.out.println(ch);//o
		```

	- 获取参数字符串在本字符串中首次出现的位置

		```java
		public int indexOf(String string){}
		//1.参数字符串首次出现的位置，后面的不管
		//2.如果不存在，返回-1
		```

	- 

	- 

- ##### 字符串的截取

	- substance(int index)方法

		```java
		public String substance(int index){}
		//截取从参数位置一直到结束，返回字符串
		String str1 = "Hello";
		String str2 = str1.substance(1);
		System.out.println(str2);//2
		```

	- substance(int begin , int end)方法

		```java
		public String substance(int begin, int end){}
		//1.截取从begin开始，到end结束，取中间部分
		//2.[begin , end)包含左边，不包含右边
		String str3 = str1.substance(1,3);//el
		```

	- 扩展口

- ##### 字符串的转换

	- toCharArray()方法

		```java
		public char[] toCharArray(){}
		//将当前字符串拆分为字符数组，作为返回值
		String str1 = "abc";
		char[] chars = str1.toCharArray();//{'a','b','c'}
		for(int i = 0 ; i < chars.length; i++){
		    System.out.println(chars[i])
		}
		```

	- getBytes()方法

		```java
		public byte[] getBytes(){}
		//获取当前字符串底层的字符数组
		byte[] bytes = str1.getBytes();//{97,98.99}
		```

	- replace(CharSequence oldString , CharSequence)

		```java
		public String replace(CharSequence target , CharSequence replacement ){}
		//将所有老字符串(target)换成新字符串(replacement)，返回新的字符串
		String str2 = str1.replace("a","A");
		System.out.println(str2);//Abc
		```

	- 扩展口

- ##### 字符串的分割

	- split(String regex)方法

		```java
		public String[] split(String regex){}
		//按照参数的规则，将字符串切割成若干部分
		String str1 = "aaa,bbb,ccc";
		String[] strArray= str1.split(",");
		for(int i = 0 ; i < strArray.length; i++){
		    System.out.println(strArray[i])
		}
		//aaa 
		//bbb 
		//ccc
		```

		【注意事项】

		1. split方法的参数是一个“正则表达式”

		2. 如果按照英文句点"."进行切割，必须写"\\\\."(两个反斜杠)

			```java
			String str1 = "aaa.bbb.ccc";
			String[] strArray= str1.split("\\.");
			```

	- 

	- 

- 

- #### 

#### Arrays

- 【**功能**】：是一个与数组有关的工具类，里面提供了大量静态方法，用来实现数组的常见操作

- **使用步骤**：

  - 导包

  	````java
  	import java.util.Arrays;
  	````

  - 使用

  	1. 将参数数组变成字符串

  		- 格式：**public static String  toString(数组)**

  			````java
  			int[] array = {};
  			String str = Arrays.toString(array);//把数组变成字符串
  			System.out.println(array);//[]
  			````

  	2. 对数组进行排序

  		- 格式：**public static  void sort (数组)**

  			````java
  			int[] array = {1,2,4,3,0};
  			Arrays.sort(array);//按照默认升序（从大到小）方式对数组进行排序,无返回值
  			System.out.println(Arrays.toString(array));//[0,1,2,3,4]
  			````

  	3. 

  - 


- 

#### Math

#### 猜数字案例

## 第二阶段	  Java语言进阶

### 常用API

#### Date

#### DateFormat

#### Calendar

#### System

- 概念

- 【注意】System类不能被实例化

- 使用步骤

	- System是指java.lang.System下，所以不用“导包”
	- System不能被实现化，所以也不用“创建”
	- System中的方法都是静态方法，所以通过**类名称.方法名()**使用
	- 

- 常用方法

	- **运行垃圾回收器**，其实是调用Object当中的finalize()

		```java
		public static void gc()
		```

	- **终止当前虚拟机的运行**

		```java
		public static void exit (int status)
		//参数 status：表示退出状态
		//0表示正常退出，非0的状态表示异常终止
		```

	- **返回以毫秒为单位的当前时间**

		```java
		public static long currentTimeMillis()
		//返回：当前时间与协调世界时 1970 年 1 月 1 日午夜之间的时间差（以毫秒为单位测量）
		```

	- **复制一个数组到另一个数组**

		```java
		public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)
		//src：源数组
		//srcPos：源数组中的起始位置
		//dest：目标数组
		//destPos：目标数组中的起始位置
		//length：要复制的元素的个数
		```

	- 

- 

- 

#### StringBuffer

- **概念**

	- 一个类似于String的字符缓冲区
	- 【注意】
		1. 每个字符串缓冲区都有一定的容量
		2. 如果内部缓冲区溢出，则此容量自动增大
	- String与StringBuffer区别
		1. String是一个不可变的字符序列
		2. StringBuffer是一个可变的字符序列
		3. StringBuffer不能使用“+”与其他类型连接
	- 

- **构造方法**

	- 无参构造

		````java
		StringBuffer sb = new StringBuffer();//其初始容量为16个字符
		````

	- 全参构造

		1. StringBuffer(CharSequence seq) 参数：其实现类的对象

			````java
			StringBuffer sb = new StringBuffer(new String());
			````

		2. StringBuffer(int capacity) 指定初始容量

			````java
			StringBuffer sb = new StringBuffer(10);//初始容量由默认16变成10
			````

		3. StringBuffer(String str)将其内容初始化为指定的字符串内容

			````java
			StringBuffer sb = new StringBuffer("Hello");
			````

	- 

- **常用方法**

	- 添加功能

		1. append(参数列表)：向StringBuffer中**追加**元素,返回缓冲区本身

		````java
		public StringBuffer append(String str)//参数：追加的类型很多
		
		StringBuffer sb1 = sb.append("Hello"); 
		或者
		sb.append("Hello");//省略前面用于接收返回的值，这是因为在原来的基础上追加
		````

		2. insert(参数列表)：向StringBuffer中**插入**元素，返回缓冲区本身

		````java
		public StringBuffer insert(int offset, String str)//插入的类型很多
		//参数：offset —— 偏移量，类似索引位置，从0开始
		    
		sb.insert(1，"123");//H123ello
		````

	- 删除功能

		1. deleteCharAt(参数列表)：删指定位置的字符，返回缓冲区本身

			````java
			public StringBuffer deleteCharAt(int index)
			````

		2. delete(参数列表)：删除从开始位置到结束位置之间的字符，返回缓冲区本身

			````java
			public StringBuffer delete(int start, int end)
			//参数：索引从0开始，[start, end)
			 sb.delete(1,4);//Hello
			````

	- 转换换功能

		1. replace(参数列表)：替换StringBuffer中的字符，返回缓冲区本身

			````java
			public StringBuffer replace(int start, int end, String str)
			//参数：开始索引位置，结束索引位置，[start, end)
			sb.replace(1,5,"ELL");//HELLO
			````

		2. reserve():将stringBuffer中字符顺序进行反转

			````java
			pulic StringBuffer reserve()
			sb.reserve();//OLLEH
			````

	- 获取长度功能

		1. length():返回字符长度（实际长度）
		2. capacity()：返回当前容量（理论长度）

	- 截取功能

		1. substring(参数列表)：截取指定位置到末尾，返回**字符串类型**

			````java
			public String substring(int index)
			````

		2. substring(参数列表)：截取开始位置到结束位置之间的字符，**返回字符串类型**

			````java
			public String substring(int start, int end)
			String str = sb.substring(0,3);//OLL
			````

	- 

- **StringBuffer与String的相互转换**

	- StringBuffer——>String

		1. 全参构造方法

			````java
			StringBuffer sb = new StringBuffer("Hello");
			String str = new String(sb);
			````

		2. toString方法

			````java
			String str = sb.toString();
			````

		3. substing(0,sb.length())

			````java
			String str = sb.substring(0,5)
			````

	- String——>StringBuffer

		1. 无参构造+append方法

			````java
			StringBuffer sb = new StringBuffer();
			sb.append("Hello")
			````

		2. 全参构造

			````java
			StringBuffer sb = new StringBuffer("Hello");
			````

			

- 

- 

#### StringBuilder

#### Collection常用集合

#### Iterator

#### IO流

#### 泛型

#### Map转换流

### 多线程和网络编程

#### 多线程编程和原理

#### 线程生命周期

#### 线程同步

#### 线程池

#### Socket原理

#### UDP传输

#### TCP传输

#### 文件上传案例

### Lambda表达式与新特性

#### 函数式编程思想

#### Lambda标准格式

#### Lambda语法

#### 函数式接口

#### 方法引用

#### 函数式编程

#### Stream流

## 第三阶段	  JavaWeb

### 数据库基础

#### MySQL数据库

#### JDBC开发

#### 连接池

#### JDBC事务管理

#### 转账案例

#### Spring JdbcTemplate

### 网页开发基础

#### HTML

#### CSS

#### Javascript

#### BootStrap

#### 黑马旅游首页

### Linux操作系统基础

#### Linux安装

#### 目录

#### 文件

#### 网络

#### nginx安装

#### 配置

### Java基础加强

#### 反射

#### BeanUtils

#### 注解

### 爬虫技术基础

#### xml基本语法

#### DTD和Schema约束

#### jsoup使用

#### xpath

### JavaWeb核心

#### Tomcat

#### Servlet

#### Cookie

#### Session

#### JSP

#### EL

#### JSTL

#### Filter

#### Listener

#### 文件下载

### Ajax异步编程

#### Ajax原理

#### jQuery Ajax

#### 账号校验案例

#### 省市联动案例

### JavaWeb综合实践

#### Redis数据类型

#### 常用命令

#### Jedis

#### BaseServlet抽取

#### Redis缓存

#### Linux Shell编程

#### 项目部署

#### 黑马旅游网

## 第四阶段	  项目一

### MyBatis3框架

#### 自定义Mybatis框架

#### Mybatis架构分析

#### 常用API

#### 配置与事物管理

#### mapper代理

#### 数据封装

#### 动态sql

#### 关联查询

#### 性能优化

#### 查询缓存

### Spring5框架

#### 配置详解

### IoC

### DI

### AOP

### AspectJ

#### 声明式事物管理

### SpringMVC框架

#### 框架原理及入门案例

#### 控制器

#### 常用注解

#### 参数绑定

#### json数据交换

#### restful

#### 拦截器

#### 文件上传

#### 异常处理

### Oracle数据库

#### 常用函数

#### 多表查询

#### 集合操作

#### 数据库对象

#### PL/SQL编程

#### 存储过程与存储函数

#### 触发器

### Maven项目管理

#### Maven安装配置

#### Maven常用命令

#### 依赖管理

#### 多模块和继承

#### Nexus私服

### 企业级权限管理系统

#### SVN版本控制

#### AdminLTE

#### SSM注解整合

#### Spring  Security权限控制

#### AOP日志管理

### 物流行业——国际物流

#### Maven分模块构建

#### Git版本控制

#### DUbbox分布式服务

#### Angular JS前端框架

#### ActiveMQ消息队列

#### 代码生成器

#### Spring Security权限控制

#### Solr数据搜索

#### 阿里大于短信

#### CAS单点登录

#### 微信扫码支付

#### 电商秒杀

#### Spring Task任务调度

### Lucene/ElasticSearch框架

#### Lucene全文检索

#### Analyzer分析器

#### 索引维护

#### ElasticSearch安装配置

#### 操作入门

#### IK分词器

#### 常用操作

#### SpringDate

#### ElasticSearch使用

## 第五阶段	  项目二

### Spring Date JPA框架

#### ORM概述

#### Hibernate

#### JPA语法

#### Spring  Date  JPA常用操作

#### Spring  Date  JPA关联映射与多表操作	

### Spring Boot框架

#### SpringBoot快速入门（包括热部署）

#### SpringBoot  Starters

#### SpringBoot原理分析

#### Thymeleaf模板

### GIT版本控制

#### 安装配置

#### 常用操作

#### 远程仓库

#### 分支管理

### VUE.JS前端框架

#### 系统指令

#### 过滤器

#### 异步交互

#### 组件

#### 路由

### 爬虫实战课程

#### 爬虫原理分析

#### httpClient实现爬虫

#### WebMagic框架

### 社交行业——十次方

#### SpringBoot/SpringCloud微服务构建

#### OSS阿里云存储

#### Elasticsearch5数据搜索

#### RabbitMQ消息中间件

#### JWT微服务鉴权

#### ELK分布式日志

#### Jenkins持续集成

#### Docker容器部署

#### Rancher容器管理

#### Node.js工程化

#### vue.js前端框架

#### ElementUI组件库

#### NUXT服务端渲染

#### webmagic爬虫

#### Spark MLlib ALS机器学习

​	