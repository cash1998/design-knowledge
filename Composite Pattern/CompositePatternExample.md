### Composite Pattern

This pattern creates a class that contains group of its own objects. This class provides ways to modify its group of same objects.

```
class GraphNode{
	List<GraphNode> adjacentNodes;
	
	void addAdjacentNode(GraphNode graphNode){
		adjacentNodes.add(graphNode);
	}
}

main(){
	GraphNode a = new GraphNode();
	GraphNode b = new GraphNode();
	GraphNode c = new GraphNode();
	GraphNode d = new GraphNode();
	GraphNode e = new GraphNode();
	
	a.addAdjacentNode(b);
	a.addAdjacentNode(c);
	
	b.addAdjacentNode(a);
	b.addAdjacentNode(d);
	b.addAdjacentNode(e);
	
	c.addAdjacentNode(e);
	
	d.addAdjacentNode(c);
	
	e.addAdjacentNode(d);
}
```
