class Node:
   def __init__(self, data):
      self.left = None
      self.right = None
      self.data = data

   def insert(self, data):
# Compare the new value with the parent node
      if self.data:
         if data < self.data:
            if self.left is None:
               self.left = Node(data)
            else:
               self.left.insert(data)
         elif data > self.data:
               if self.right is None:
                  self.right = Node(data)
               else:
                  self.right.insert(data)
      else:
         self.data = data

# Print the tree
   def PrintTree(self):
      list_tree = []
      if self.left:
         self.left.PrintTree()
      print( self.data)
      list_tree.append(self.data)
      if self.right:
         self.right.PrintTree()
   
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



# Use the insert method to add nodes
root = Node(27)
root.insert(14)
root.insert(35)
root.insert(10)
root.insert(19)
root.insert(31)
root.insert(42)
root.PrintTree()
print(root.levelorderTraversal(root))   


