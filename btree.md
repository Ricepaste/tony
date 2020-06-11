# 6-7-2
```python=
class Node():
    def __init__(self, data=None):
        self.data = data
        self.left = None
        self.right = None
    
    def print_root(self):
        print(self.data)

    def insert(self, data):
        if self.data:
            if data < self.data:
                if self.left:
                    self.left.insert(data)
                else:
                    self.left = Node(data)
            else:
                if self.right:
                    self.right.insert(data)
                else:
                    self.right = Node(data)
        else:
            self.data = data
    
    def postorder(self):
        deep = 0
        left = 0
        right = 0
        if self.left:
            left = self.left.postorder() + 1
        if self.right:
            right = self.right.postorder() + 1
        print(self.data)
        if not(self.left or self.right):
            return 1
        deep = max(left, right)
        return deep


tree = Node()
x = list(map(int, input().split()))
for i in x:
    tree.insert(i)
lf = None
lf = tree.postorder()
print('深度:', lf)

```