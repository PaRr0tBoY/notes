Arrays是专为数组而生的工具类。

用Arrays创建数组可以使用copyOf、copyOfRange、fill这三个方法

## 创建数组
### copyOf

```java
int[] test = new int[] {1,2,3};
int[] revised = Arrays.copyOf(test,2);
int[] expanded = Arrays.copyOf(test,4);
System.out.println(Arrays.toString(revised));
System.out.println(Arrays.toString(expanded));

//输出结果为
[1,2]
[1,2,3,0]
```

copyOf(数组, 索引), 数组之后的数字代表从左开始检索的次数,如果超过了数组的长度,就会用数组相应的元素类型默认值填补, 比如int类型就填0, String类型就填 null ;\
### copyOfRange

```java
String[] intro = new String[] {"我", "操", "你", "妈"};
String[] test = Arrays.copyOfRange(intro, 1, 3);
System.out.println(Arrays.toString(test));

//输出结果为
[操,你]
//相当的友好
//如果是1,5,输出结果为
[操,你,妈,null]
```

考虑到数组越界问题,为了避免每次使用Arrays都判断很多次长度,所以超出数组长度时会自动填补默认值。

### fill

```java
String[] stutter = new String[4];
Arrays.fill(stutter, "啊");
System.out.println(Arrays.toString(stutter));

//输出结果为
[啊, 啊, 啊, 啊]
```

fill方法将"啊"复制到数组中的每一个空位置。

## 比较数组

### equals

equals方法对于字符串来说是比较内容的，而对于非字符串来说是比较其指向的对象是否相同的。== 比较符也是比较指向的对象是否相同的也就是对象在对内存中的首地址。
String类中重新定义了equals这个方法，而且比较的是值，而不是地址

Arrays类中的equals方法用于比较两个数组是否相等，主要比较内容是否相等，如果引用相等，那么内容一定相等；引用不相等，也不影响equals方法返回两个内容相等的数组为true。

```java
public class equalsTest1{
	public static void main(String[] args){
		String[] array = String[] {"abc", "123"};
		String[] result = Arrays.equals(new String[] {"abc", "123"}, array);
		System.out.println(result);
		String[] result = Arrays.equals(new String[] {"abc", "123"}, array);
		System.out.println(result);
	}
}
```

### hashCode

比较两个数组的哈希码也可以比较二者内容是否相同

```java
String[] intro = String[] {"我","去"};
System.out.println(Arrays.hashCode(intro));
SYstem.out.println(Arrays.hashCode(new String[] {"我","去"}))
```

## 排序数组

### sort

```java
String[] sorted = Arrays.copyOf(intro, intro.length);  
Arrays.sort(sorted);  
System.out.println(Arrays.toString(sorted));
```

因为sorted会改变原来的数组,所以用copyOf提前复制了一份前文的intro。

## 检索数组

```java
String[] intro1 = new String[] { "chen", "mo", "wang", "er" };
String[] sorted = Arrays.copyOf(intro1, 4);
Arrays.sort(sorted);
int exact = Arrays.binarySearch(sorted, "wang");
System.out.println(exact);
int caseInsensitive = Arrays.binarySearch(sorted, "Wang", String::compareToIgnoreCase);
System.out.println(caseInsensitive);
```

来自二哥java的数组检索实例,利用binarySearch方法查询数组,比线性查找要快,也可以忽略大小写模糊查询。

## 打印数组

直接用`System.out.println(intro)`来打印数组会得到`[Ljava.lang.String;@2f4d3709`这样的结果,用toString打印数组是最优雅的。

```java
System.out.println(Arrays.toString(intro));
```

### setAll

setAll方法提供了一个函数式编程的入口,可以对数组的元素进行填充;

```java
int[] array = new int[10];
Arrays.setAll(array, i -> i * 10);
System.out.println(Arrays.toString(array))

//输出结果
[0, 10, 20, 30, 40, 50, 60, 70, 80, 90]
```

i 就相当于是数组的下标，值从 0 开始，到 9 结束，那么 `i * 10` 就意味着值从 0 * 10 开始，到 9 * 10 结束

### parallelPrefix

```java
int[] arr = new int[] { 1, 2, 3, 4};
Arrays.parallelPrefix(arr, (left, right) -> left + right);
System.out.println(Arrays.toString(arr));
```

1. `int[] arr = new int[] { 1, 2, 3, 4};` 创建了一个包含四个整数的数组。
2. `Arrays.parallelPrefix(arr, (left, right) -> left + right);` 调用 `Arrays.parallelPrefix` 方法：
    - 第一个参数是数组 `arr`。
    - 第二个参数是一个 `BinaryOperator<Integer>` 的 lambda 表达式，定义了如何计算前缀和。这里使用的是 `(a, b) -> a + b`，即数组元素的和。
3. `System.out.println(Arrays.toString(arr));` 打印数组的内容。

### 输出结果

执行这段代码后，输出结果将是：

`[1, 3, 6, 10]`

### 详细说明

`Arrays.parallelPrefix` 方法的工作原理如下：

- 初始时，数组的第一个元素保持不变（这里是1）。
- 从第二个元素开始，每个元素的值被更新为其前一个元素和当前元素的和。例如：
    - 第二个元素的值更新为 `1 + 2`（即3）。
    - 第三个元素的值更新为 `3 + 3`（即6）。
    - 第四个元素的值更新为 `6 + 4`（即10）。

这种方法特别适用于需要并行计算的场景，可以提高计算效率。