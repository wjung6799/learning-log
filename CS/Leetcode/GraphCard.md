# Graph

## Disjoint Set

### Quick Find

```python
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

### Quick Union

```python
# UnionFind class
class UnionFind:
    def __init__(self, size):
        self.root = [i for i in range(size)]

    def find(self, x):
        while x != self.root[x]:
            x = self.root[x]
        return x
		
    def union(self, x, y):
        rootX = self.find(x)
        rootY = self.find(y)
        if rootX != rootY:
            self.root[rootY] = rootX

    def connected(self, x, y):
        return self.find(x) == self.find(y)
```

### Union By Rank

```python
# UnionFind class
class UnionFind:
    def __init__(self, size):
        self.root = [i for i in range(size)]
        self.rank = [1] * size

    def find(self, x):
        while x != self.root[x]:
            x = self.root[x]
        return x
		
    def union(self, x, y):
        rootX = self.find(x)
        rootY = self.find(y)
        if rootX != rootY:
            if self.rank[rootX] > self.rank[rootY]:
                self.root[rootY] = rootX
            elif self.rank[rootX] < self.rank[rootY]:
                self.root[rootX] = rootY
            else:
                self.root[rootY] = rootX
                self.rank[rootX] += 1

    def connected(self, x, y):
        return self.find(x) == self.find(y)
```

### Path Compression Optimization

```python
# UnionFind class
class UnionFind:
    def __init__(self, size):
        self.root = [i for i in range(size)]

    def find(self, x):
        if x == self.root[x]:
            return x
        self.root[x] = self.find(self.root[x])
        return self.root[x]
		
    def union(self, x, y):
        rootX = self.find(x)
        rootY = self.find(y)
        if rootX != rootY:
            self.root[rootY] = rootX

    def connected(self, x, y):
        return self.find(x) == self.find(y)
```

### Optimized

```python
# UnionFind class
class UnionFind:
    def __init__(self, size):
        self.root = [i for i in range(size)]
        # Use a rank array to record the height of each vertex, i.e., the "rank" of each vertex.
        # The initial "rank" of each vertex is 1, because each of them is
        # a standalone vertex with no connection to other vertices.
        self.rank = [1] * size

    # The find function here is the same as that in the disjoint set with path compression.
    def find(self, x):
        if x == self.root[x]:
            return x
        self.root[x] = self.find(self.root[x])
        return self.root[x]

    # The union function with union by rank
    def union(self, x, y):
        rootX = self.find(x)
        rootY = self.find(y)
        if rootX != rootY:
            if self.rank[rootX] > self.rank[rootY]:
                self.root[rootY] = rootX
            elif self.rank[rootX] < self.rank[rootY]:
                self.root[rootX] = rootY
            else:
                self.root[rootY] = rootX
                self.rank[rootX] += 1

    def connected(self, x, y):
        return self.find(x) == self.find(y)
```

| Syntax      | Union-find Constructor | Find | Union | Connected |
| ----------- | ----------- |---|---|---|
| Quick Find  | O(N)       | O(1) | O(N) | O(1) |
| Quick Union | O(N)       | O(N) |  O(N) |  O(N) |
| Union By Rank | O(N)       | O(log N) |  O(log N) |  O(log N) |
| Path Compression | O(N)       | O(log N) |  O(log N) |  O(log N) |
| Optimized | O(N) | O(&alpha;(N)) | O(&alpha;(N)) | O(&alpha;(N)) |

Note: NNN is the number of vertices in the graph. &alpha; refers to the Inverse Ackermann function. In practice, we assume it's a constant. 


Problems:

1. https://leetcode.com/problems/smallest-string-with-swaps/
2. https://leetcode.com/problems/evaluate-division/

	for this one watch https://www.youtube.com/watch?v=paePJDgZaR4
	
```python
class Solution:
    def calcEquation(self, equations: List[List[str]], values: List[float], queries: List[List[str]]) -> List[float]:
        items = set()
        
        uf = DisjointSet(items)
        
        for i in range(len(equations)):
            u, v = equations[i]
            weight = values[i]
            uf.union(u, v, weight)
        
        ret = []
        
        for u, v in queries:
            if u not in uf.weight or v not in uf.weight:
                ret.append(-1.0)
            else:
                u, uWeight = uf.find(u)
                v, vWeight = uf.find(v)
                if u != v:
                    ret.append(-1.0)
                else:
                    ret.append(uWeight/vWeight)
        
        return ret

class DisjointSet:
    
    def __init__(self, items):
        self.weight = {}
    
    def find(self, u):
        if u not in self.weight:
            self.weight[u] = (u, 1.0)
        
        parent, nodeWeight = self.weight[u]
        if u != parent:
            newParent, parentWeight = self.find(parent)
            self.weight[u] = (newParent, nodeWeight * parentWeight)
        
        return self.weight[u]
        
    
    def union(self, u, v, val):
        u, uWeight = self.find(u)
        v, vWeight = self.find(v)
        if u != v:
            self.weight[u] = (v, val * vWeight / uWeight)
```
