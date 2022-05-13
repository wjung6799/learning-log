# DFS

## Iterative DFS
```python
class Graph:
    def __init__(self,V): # Constructor
        self.V = V        # No. of vertices
        self.adj  = [[] for i in range(V)]  # adjacency lists
 
    def addEdge(self,v, w):     # to add an edge to graph
        self.adj[v].append(w)    # Add w to v’s list.
 
 
    # prints all not yet visited vertices reachable from s
    def DFS(self,s):            # prints all vertices in DFS manner from a given source.
                                # Initially mark all vertices as not visited
        visited = [False for i in range(self.V)]
 
        # Create a stack for DFS
        stack = []
 
        # Push the current source node.
        stack.append(s)
 
        while (len(stack)):
            # Pop a vertex from stack and print it
            s = stack[-1]
            stack.pop()
 
            # Stack may contain same vertex twice. So
            # we need to print the popped item only
            # if it is not visited.
            if (not visited[s]):
                print(s,end=' ')
                visited[s] = True
 
            # Get all adjacent vertices of the popped vertex s
            # If a adjacent has not been visited, then push it
            # to the stack.
            for node in self.adj[s]:
                if (not visited[node]):
                    stack.append(node)
 
 
 
# Driver program to test methods of graph class
 
g = Graph(5); # Total 5 vertices in graph
g.addEdge(1, 0);
g.addEdge(0, 2);
g.addEdge(2, 1);
g.addEdge(0, 3);
g.addEdge(1, 4);
 
print("Following is Depth First Traversal")
g.DFS(0)
```


## Recursive DFS

```python
# Python3 program to print DFS traversal
# from a given graph
from collections import defaultdict

# This class represents a directed graph using
# adjacency list representation


class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# A function used by DFS
	def DFSUtil(self, v, visited):

		# Mark the current node as visited
		# and print it
		visited.add(v)
		print(v, end=' ')

		# Recur for all the vertices
		# adjacent to this vertex
		for neighbour in self.graph[v]:
			if neighbour not in visited:
				self.DFSUtil(neighbour, visited)

	# The function to do DFS traversal. It uses
	# recursive DFSUtil()
	def DFS(self, v):

		# Create a set to store visited vertices
		visited = set()

		# Call the recursive helper function
		# to print DFS traversal
		self.DFSUtil(v, visited)

# Driver code


# Create a graph given
# in the above diagram
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print("Following is DFS from (starting from vertex 2)")
g.DFS(2)

# This code is contributed by Neelam Yadav
```


1. https://leetcode.com/problems/clone-graph/
2. https://leetcode.com/problems/reconstruct-itinerary/
