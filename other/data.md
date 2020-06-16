题目一的测试数据：

1. 测试用例1
```ini
input:
4 6
1 2 1 2 1
1 4 2 1 1 
2 4 2 1 1
1 3 4 3 0
2 3 3 4 0
3 4 5 5 0
output:
3
3
```

   

2. 测试用例2：
```ini
input:
5 7
1 3 3 4 0
3 4 2 5 0
1 5 4 4 0
2 5 5 4 0
1 4 3 3 1
1 2 2 5 1
2 4 1 4 1
output:
6
8
```

3. 测试用例3：
```ini
input:
5 5
1 4 4 5 0
4 5 3 4 0
3 4 2 3 0
3 5 2 2 1
1 2 1 2 1
output:
6
8
```

4. 测试用例4：
```ini
input:
5 7
1 4 2 2 0
1 3 3 2 0
1 5 1 4 0
2 5 1 5 0
2 3 2 3 1
2 4 1 1 1
3 4 4 3 1
output:
2
6
```

题目二的测试数据：

1. 测试用例1
```Java
Node node1 = new Node(1,new ArrayList());
Node node2 = new Node(2,new ArrayList());
Node node3 = new Node(3,new ArrayList());
Node node4 = new Node(4,new ArrayList());
node1.neighbors.add(node2);
node1.neighbors.add(node4);
node2.neighbors.add(node1);
node2.neighbors.add(node3);
node3.neighbors.add(node2);
node3.neighbors.add(node4);
node4.neighbors.add(node1);
node4.neighbors.add(node3);
```

2. 测试用例2
```Java
Node node1 = new Node(1,new ArrayList());
Node node2 = new Node(2,new ArrayList());
Node node3 = new Node(3,new ArrayList());
Node node4 = new Node(4,new ArrayList());
Node node5 = new Node(5,new ArrayList());
node1.neighbors.add(node2);
node1.neighbors.add(node4);
node2.neighbors.add(node1);
node2.neighbors.add(node3);
node3.neighbors.add(node2);
node3.neighbors.add(node4);
node3.neighbors.add(node5);
node4.neighbors.add(node1);
node4.neighbors.add(node3);
node4.neighbors.add(node5);
node5.neighbors.add(node3);
node5.neighbors.add(node4);
```

3. 测试用例3
```Java
Node node1 = new Node(1,new ArrayList());
Node node2 = new Node(2,new ArrayList());
Node node3 = new Node(3,new ArrayList());
Node node4 = new Node(4,new ArrayList());
Node node5 = new Node(5,new ArrayList());
node1.neighbors.add(node2);
node1.neighbors.add(node4);
node1.neighbors.add(node5);
node2.neighbors.add(node1);
node2.neighbors.add(node3);
node3.neighbors.add(node2);
node3.neighbors.add(node4);
node3.neighbors.add(node5);
node4.neighbors.add(node1);
node4.neighbors.add(node3);
node4.neighbors.add(node5);
node5.neighbors.add(node3);
node5.neighbors.add(node4);
node5.neighbors.add(node1);
```

4. 测试用例4
```Java
Node node1 = new Node(1,new ArrayList());
Node node2 = new Node(2,new ArrayList());
Node node3 = new Node(3,new ArrayList());
Node node4 = new Node(4,new ArrayList());
Node node5 = new Node(5,new ArrayList());
Node node6 = new Node(6,new ArrayList());
node1.neighbors.add(node2);
node1.neighbors.add(node4);
node1.neighbors.add(node5);
node1.neighbors.add(node6);
node2.neighbors.add(node1);
node2.neighbors.add(node3);
node3.neighbors.add(node2);
node3.neighbors.add(node4);
node3.neighbors.add(node5);
node4.neighbors.add(node1);
node4.neighbors.add(node3);
node4.neighbors.add(node5);
node5.neighbors.add(node3);
node5.neighbors.add(node4);
node5.neighbors.add(node1);
node6.neighbors.add(node1);
```

5. 测试用例5
```Java

```














