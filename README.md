# -Algorithm-Binary_tree_traversal
Constructed tree and practice three different traversal algorithm
### 簡介：

主要的目的是用來走訪二元樹中各個節點，並且轉換為線性關係。

分成策略

1. 深度優先搜尋(DFS): 先訪問完子節點後再選擇另一子樹走訪
    1. 前序走訪(Pre-order Traversal)NLR: 根-左-右
    2. 中序走訪(In-order Traversal)LNR: 左-根-右
    3. 後續走訪(Post-order Traversal)LRN: 左-右-根
2. 廣度優先搜尋(BFS): 以水平方向由左至右，將同階層的兄弟走訪完之後再往下一階層前進
    1. 層序走訪(Level-order Traversal) 

### 舉例：

```python
def inorderTraversal(self, root):
      res = []
      if root:
         res = self.inorderTraversal(root.left)
         res.append(root.data)
         res = res + self.inorderTraversal(root.right)
      return res

def preorderTraversal(self, root):
      res = []
      if root:
         res.append(root.data)
         res = res + self.preorderTraversal(root.left)
         res = res + self.preorderTraversal(root.right)
      return res
   
   def postorderTraversal(self, root):
      res = []
      if root:
         res = self.postorderTraversal(root.left)
         res = res + self.postorderTraversal(root.right)
         res.append(root.data)
      return res
   
   def levelorderTraversal(self, root):
      d = dict()
      def bfs(root,level):
         if not root: return
         if level in d.keys():
            d[level].append(root.data)
         else:
            d[level] = [root.data]
         bfs(root.left,level+1)
         bfs(root.right,level+1)
      
      bfs(root,0)
      return d.values()
```

## 注意：

以上的方法都透過遞迴來完成，最後一個level order則是搭配了dictionary 的技巧
