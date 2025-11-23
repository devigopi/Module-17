# Ex. No: 17A - Generate a Graph for a Given Fixed Degree Sequence

## AIM:
To write a Python program to demonstrate the adjacency list representation of the graph.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**:Read the number of vertices n.


**Step 3**: Create an empty adjacency list

          Example: an array or dictionary with n empty lists

          adj_list = {0:[], 1:[], ..., n-1:[]}

**Step 4**: Read the number of edges e.

**Step 5**: Repeat for each edge from 1 to e:

          Read the two vertices u and v

          Insert v into the adjacency list of u

          Insert u into the adjacency list of v (for an undirected graph)
**Step 6**:After all edges are processed, the adjacency list is complete.
**Step 7**:Display the adjacency list

            For each vertex i, print all nodes inside adj_list[i].
**Step 8**:End the program

## PYTHON PROGRAM

```

class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None


# A class to represent a graph. A graph
# is the list of the adjacency lists.
# Size of the array will be the no. of the
# vertices "V"
class Graph:
	def __init__(self, vertices):
		self.V = vertices
		self.graph = [None] * self.V

	# Function to add an edge in an undirected graph
	def add_edge(self, src, dest):
		# Adding the node to the source node
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node

		# Adding the source node to the destination as
		# it is the undirected graph
		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	
	def print_graph(self):
	    for i in range(self.V):
	        print("Adjacency list of vertex {}\n head".format(i),end="")
	        temp=self.graph[i]
	        while temp:
	            print(" -> {}".format(temp.vertex),end="")
	            temp=temp.next
	        print(" \n")





# Driver program to the above graph class
if __name__ == "__main__":
	V = 5
	graph = Graph(V)
	graph.add_edge(0, 1)
	graph.add_edge(0, 4)
	graph.add_edge(1, 2)
	graph.add_edge(1, 3)
	graph.add_edge(1, 4)
	graph.add_edge(2, 3)
	graph.add_edge(3, 4)

	graph.print_graph()
```

## OUTPUT
<img width="727" height="377" alt="image" src="https://github.com/user-attachments/assets/fdae839a-9690-4e11-bde7-77504ab685a0" />


## RESULT
      Thus the program to demonstrate the adjacency list representation of the graph is successively verified.
