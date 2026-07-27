ExpNo 2 : Implement Depth First Search Traversal of a Graph

Name: MOHANA K.V.S.L

Register Number : 212224240093

Aim:

To Implement Depth First Search Traversal of a Graph using Python 3.

Theory:

Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. Step 1: Initially, stack and visited arrays are empty.

<img width="1472" height="737" alt="image" src="https://github.com/user-attachments/assets/d9b2ed2e-a164-4a6a-a6aa-b0eb042d9fc4" />


Queue and visited arrays are empty initially. Stack and visited arrays are empty initially. Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack. 


<img width="1326" height="665" alt="image" src="https://github.com/user-attachments/assets/0ad32f66-86f2-497a-9e1f-571567db6f2e" />


Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. 


<img width="1262" height="627" alt="image" src="https://github.com/user-attachments/assets/f2b951fa-b4b7-4e45-b730-cbebe4947e53" />


Visit node 1 Visit node 1

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack. 


<img width="1517" height="762" alt="image" src="https://github.com/user-attachments/assets/0a9619ac-f146-46c9-8afa-a0b331b13847" />


Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. 


<img width="1546" height="777" alt="image" src="https://github.com/user-attachments/assets/b766dbe8-b9f5-4f9b-8791-c402709af5c1" />


Visit node 4 Visit node 4

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.


<img width="1362" height="683" alt="image" src="https://github.com/user-attachments/assets/64c75dfa-71d6-4a47-8609-f14f105bd094" />


Visit node 3 Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

Algorithm:

Construct a Graph with Nodes and Edges
Depth First Search Uses Stack and Recursion
Insert a START node to the STACK
Find its Successors Or neighbors and Check whether the node is visited or not
If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.
Sample Input
8 9
A B
A C
B E
C D
B D
C G
D F
G F
F H

Sample Output
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']

Sample Input
5 5
0 1
0 2
0 3
2 3
2 4

Sample Output
['0', '1', '2', '3', '4']

CODE:
```


from collections import defaultdict

def dfs(graph, start, visited, path):
    visited[start] = True

    path.append(start)

    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)

    return path


graph = defaultdict(list)

n, e = map(int, input("Enter number of vertices and edges: ").split())

print("Enter the edges:")

for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)   

start = 'A'      


visited = defaultdict(bool)

path = []

traversed_path = dfs(graph, start, visited, path)

print("DFS Traversal:")
print(" -> ".join(traversed_path))
```
OUTPUT:

<img width="1195" height="550" alt="image" src="https://github.com/user-attachments/assets/0aef0344-d583-4a40-8c47-f7cba3c5a968" />

RESULT

Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.

