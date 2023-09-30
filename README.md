# Hill_climbing_algorithm
Starts with the source node choose the neighbour with the highest value, Move to the node with the highest value, choose the node with the highest value, and move to the next highest node value and so on. The Hill climbing starts with the source node and navigates the graph to find the destination with the highest cumulative value.  
import networkx as nx
import matplotlib.pyplot as plt

# Create a directed graph
G = nx.DiGraph()

# Add nodes
nodes = ['S', 'A', 'B', 'C', 'D', 'E', 'G']
G.add_nodes_from(nodes)

# Add edges with assigned values
edges = [
    ('S', 'A', 3), ('S', 'B', 5), ('A', 'D', 4), ('B', 'C', 4), ('C', 'E', 6), ('D', 'G', 5)
]
G.add_weighted_edges_from(edges)

# Define the layout for node positioning
pos = {
    'S': (0, 0),
    'A': (1, 1),
    'B': (1, -1),
    'C': (2, -1),
    'D': (2, 1),
    'E': (3, -1),
    'G': (3, 1)
}
# Draw the directed graph with edge weights
edge_labels = {(u, v): d['weight'] for u, v, d in G.edges(data=True)}

nx.draw(G, pos, with_labels=True, node_size=500, node_color='skyblue', font_size=10, font_color='black')
nx.draw_networkx_edge_labels(G, pos, edge_labels=edge_labels, font_color='red')

# Show the plot
plt.title('Node-to-Node Diagram with Edge Weights')
plt.axis('off')
plt.show()
