#JAVA Collection各接口的特性和应用场景#
1. List: 有序可重复的集合，每个元素都有对应的索引
 * ArrayList: 可以动态增长，允许再分配，缺点是删除元素时代价大
 * Vector:
  + Stack
3. LinkedList: 从链表中删除元素很容易，JAVA中都是doubly linked
2.Set: 没有顺序，不能包含重复元素
2.1.HashSet: 使用HASH算法来存储，有良好的存取查找性能，使用.equals()方法比较相等
2.1.1.LinkedHashSet: 使用链表保存元素次序的HashSet
2.2.SortedSet: 排序操作
2.2.1TreeSet:
2.3.EnumSet: 枚举类
3.Queue: 模拟“队列”的数据结构，头部保存最长的，尾部保存最短的，新元素offer到尾部，poll返回头部元素，不允许随机访问队列中元素
3.1.PriorityQueue: 最终结果按元素大小重排列
3.2.Deque: 双端队列，可以同时从两端添加、删除元素
ArrayDeque: 基于数组的双端队列，动态、可重新分配