# Graphs
A graph is a mathematical structure consisting of vertices (nodes) and edges (connections) that represent relationships between pairs of vertices. 
Graphs are used to model a wide range of real-world systems, networks, and relationships, enabling the study of connections, paths, and properties 
within various contexts such as computer science, social networks, transportation systems, and more.

There are different ways to store graphs, each with its own advantages and disadvantages in terms of efficiency and ease of accessing information. 
Some common ways to store graphs include:

Adjacency Matrix: It is a two-dimensional array where rows and columns represent the nodes of the graph. If node i is connected to node j,
then the value at position (i, j) (or (j, i) if the graph is undirected) will be 1 or some weight associated with the connection. 
This representation is efficient for dense graphs but may be inefficient in terms of space for sparse graphs.
```c++
#include <iostream>
#include <vector>
using namespace std;

class AdjacencyMatrixGraph {
private:
    int num_vertices;
    vector<vector<int>> graph;

public:
    AdjacencyMatrixGraph(int vertices) : num_vertices(vertices) {
        graph.assign(num_vertices, vector<int>(num_vertices, 0));
    }

    void addEdge(int v1, int v2, int weight = 1) {
        graph[v1][v2] = weight;
        // For undirected graphs, uncomment the line below
        // graph[v2][v1] = weight;
    }

    void printGraph() {
        for (int i = 0; i < num_vertices; ++i) {
            for (int j = 0; j < num_vertices; ++j) {
                cout << graph[i][j] << " ";
            }
            cout << endl;
        }
    }
};

// Example usage:
int main() {
    int num_vertices = 4;
    AdjacencyMatrixGraph graph(num_vertices);
    graph.addEdge(0, 1);
    graph.addEdge(0, 2);
    graph.addEdge(1, 2);
    graph.addEdge(2, 3);
    graph.printGraph();
    return 0;
}
```

Adjacency List: Consists of a list of links for each node in the graph. Each node has a list of its neighboring nodes or connections. 
This data structure is efficient for sparse graphs since it only stores information about existing connections but may be less efficient 
for finding specific connections in dense graphs.
```c++
#include <iostream>
#include <vector>
#include <unordered_map>
using namespace std;

class AdjacencyListGraph {
private:
    unordered_map<int, vector<int>> graph;

public:
    void addEdge(int v1, int v2) {
        graph[v1].push_back(v2);
        // For undirected graphs, uncomment the line below
        // graph[v2].push_back(v1);
    }

    void printGraph() {
        for (auto& pair : graph) {
            cout << pair.first << " -> ";
            for (int neighbor : pair.second) {
                cout << neighbor << " ";
            }
            cout << endl;
        }
    }
};

// Example usage:
int main() {
    AdjacencyListGraph graph;
    graph.addEdge(0, 1);
    graph.addEdge(0, 2);
    graph.addEdge(1, 2);
    graph.addEdge(2, 3);
    graph.printGraph();
    return 0;
}
```

Edge List: Stores information about each edge or connection in the graph. Each element of the list contains information about 
the connected nodes and possibly some additional data like the weight of the edge. This structure is useful for algorithms 
that need to access all the edges of the graph.
```c++
#include <iostream>
#include <vector>
using namespace std;

class EdgeListGraph {
private:
    vector<vector<int>> edges;

public:
    void addEdge(int v1, int v2, int weight = 1) {
        edges.push_back({v1, v2, weight});
        // For undirected graphs, uncomment the line below
        // edges.push_back({v2, v1, weight});
    }

    void printGraph() {
        for (auto& edge : edges) {
            for (int value : edge) {
                cout << value << " ";
            }
            cout << endl;
        }
    }
};

// Example usage:
int main() {
    EdgeListGraph graph;
    graph.addEdge(0, 1);
    graph.addEdge(0, 2);
    graph.addEdge(1, 2);
    graph.addEdge(2, 3);
    graph.printGraph();
    return 0;
}
```

Dictionary of Dictionaries (or Dictionary of Lists): It is a more flexible data structure that can be combined with other 
structures to store graph information. For instance, a dictionary of dictionaries could use a dictionary where keys are nodes 
and values are dictionaries representing outgoing connections from that node, or they could be adjacency lists instead of dictionaries.
```c++
#include <iostream>
#include <unordered_map>
#include <vector>
using namespace std;

class DictGraph {
private:
    unordered_map<int, vector<int>> graph;

public:
    void addEdge(int v1, int v2) {
        graph[v1].push_back(v2);
        // For undirected graphs, uncomment the line below
        // graph[v2].push_back(v1);
    }

    void printGraph() {
        for (auto& pair : graph) {
            cout << pair.first << " -> ";
            for (int neighbor : pair.second) {
                cout << neighbor << " ";
            }
            cout << endl;
        }
    }
};

// Example usage:
int main() {
    DictGraph graph;
    graph.addEdge(0, 1);
    graph.addEdge(0, 2);
    graph.addEdge(1, 2);
    graph.addEdge(2, 3);
    graph.printGraph();
    return 0;
}
```
