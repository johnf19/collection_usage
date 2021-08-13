# Java Collection Framework
## ``interface`` `Iterable`
### `interface` `Collection`

#### `interface` `List`
 - 元素有序
 - 可索引查找
 - 元素可重复
 - 元素可以是`null`

 > 1. `class` `ArrayList`
 > - 可以动态增长，允许再分配（每次对`size`增长50%）
 > - 删除插入搜索中间元素慢，随机访问快
 > > - 访问O(1)，搜索插入删除O(n)
 > - 非线程安全，性能优于`Vector`低于`List`
 > - 底层为数组
 > 2. `class` `Vector`
 > - 可以动态增长，允许再分配（每次对`size`增长100%）
 > - 线程安全（使用`synchronized`修饰），性能低于`ArrayList`
 > - 底层为数组
 >> 1. `class` `Stack`
 >> - 后进先出的栈 (Last In, First Out)
 >> - 从尾部插入元素，从尾部弹出元素
 > 3. `class` `LinkedList` also `implements Deque`
 > - 非线程安全
 > - 底层为链表
 > - 相比`ArrayList`增删操作快，随机访问慢（JAVA中都为双链)
 > > - 访问搜索O(n),插入删除O(1)

#### `interface` `Set`
 - 元素无序
 - 无索引
 - 元素不可重复
 - `Set`是value都为`null`的`Map`

 > 1. `class` `HashSet`
 > - 非线程安全
 > - 使用HASH算法来存储，存取查找性能好
 > - 元素可以是`null`
 > - 元素不可重复，两元素的`HashCode()`返回值和`equals()`方法相等视为重复
 > - 底层是`HashMap`
 >> 1. `LinkedHashSet`
 >> - 同时使用链表来维护元素顺序的`HashSet`，性能低于`HashSet`，迭代访问元素时优于`HashSet`
 > 2. `class` `EnumSet`
 > - 非线程安全
 > - 元素有序，由枚举类中的定义顺序排序
 > - 元素必须是指定枚举类的枚举值
 > - 元素不能为`null`
 > - 底层不是`Map`，是`long`或数组

 > 3. `class` `TreeSet`
 > - 非线程安全
 > - 元素有序，使用自然排序（默认）或定制排序
 >> - 自然排序使用`compareTo`方法
 >> - 定制排序使用`Comparator`对象确定逻辑顺序
 > - 元素不可以是`null`
 > - 底层是红黑树
 > > - 访问搜索插入删除都为O(log(n))


#### `interface` `Queue`
 - 模拟“队列”的数据结构 (First In First Out)
 - 元素按插入先后顺序从尾到头排列
 - 新元素插入到尾部，读取时读取头部的元素，不能访问队列中元素
 > 1. `class` `PriorityQueue`
 > - 非线程安全 
 > - 元素不能为`null`
 > - 元素可以重复
 > - 按元素大小重新排列的Queue
 > - 底层是二叉树（数组）
 > > - 访问搜索插入删除都为O(log(n))
##### `interface` `Deque`
 > - 双端队列，可以同时从两端添加、删除元素
 >> 1. `class` `ArrayDeque`
 >> - 双端队列，大小可变
 >> - 元素可以是`null`
 >> - 非线程安全
 >> - 基于链表
 >> 2. `class` `LinkedList` also `implements List`
 >> - 双端队列，大小可变
 >> - 元素不可以是`null`
 >> - 非线程安全
 >> - 基于链表
 >> 3. `class` `ConcurrentLinkedDeque`
 >> - 双端队列，大小可变
 >> - 元素不可以是`null`
 >> - 线程安全（非阻塞）
 >> - 基于链表
 >> 4. `class` `LinkedBlockingDeque`
 >> - 双端队列，大小可变
 >> - 元素不可以是`null`
 >> - 线程安全（阻塞，使用非公平ReentrantLock）
 >> - 基于链表
********************

### `interface` `Map`
 - 元素有序
 - 元素由key索引
 - key不可重复，value可重复

 > 1. `class` `HashMap`
 >> 1. `class` `LinkedHashMap`
 > 2. `class` `TreeMap`
 > 3. `class` `EnumMap`
 > 4. `class` `WeakHashMap`
 > 5. `class` `IdentityHashMap` 
