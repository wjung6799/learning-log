# Graph

## Disjoint Set

### Quick Find

```
# UnionFind class
class UnionFind:
    def __init__(self, size):
        self.root = [i for i in range(size)]

    def find(self, x):
        return self.root[x]
		
    def union(self, x, y):
        rootX = self.find(x)
        rootY = self.find(y)
        if rootX != rootY:
            for i in range(len(self.root)):
                if self.root[i] == rootY:
                    self.root[i] = rootX

    def connected(self, x, y):
        return self.find(x) == self.find(y)
```
$\alpha$
\alpha

| Syntax      | Union-find Constructor | Find | Union | Connected |
| ----------- | ----------- |---|---|---|
| Quick Find  | O(N)       | O(1) | O(N) | O(1) |
| Quick Union | O(N)       | O(N) |  O(N) |  O(N) |
| Union By Rank | O(N)       | O(log N) |  O(log N) |  O(log N) |
| Path Compression | O(N)       | O(log N) |  O(log N) |  O(log N) |
| Optimized | O(N) | O($\alpha$(N)) | O($\alpha$(N)) | O($\alpha$(N)) |
### Quick Union

```
# UnionFind class
class UnionFind:
    def __init__(self, size):
        self.root = [i for i in range(size)]

    def find(self, x):
        return self.root[x]
		
    def union(self, x, y):
        rootX = self.find(x)
        rootY = self.find(y)
        if rootX != rootY:
            for i in range(len(self.root)):
                if self.root[i] == rootY:
                    self.root[i] = rootX

    def connected(self, x, y):
        return self.find(x) == self.find(y)
```
