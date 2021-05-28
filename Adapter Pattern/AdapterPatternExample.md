### Adapter Pattern- 
interface mismatch, when 2 interface wawnt to work with each other, but the type mismatch is there.
(The xml-json example)
Command is a delegator, just calls another method; But Adapter has its own intelligence, i.e does a set of operations itself to act as a mediator.

```
IXMLDataProvider{
	XMLContent getContent();
	XMLNode getNode();
}


IJsonDataProvider{
	JsonContent getContent();
	JSONNode getNode();
}


XMLDataProvider{
	XMLContent getContent(){
		//logic
	}
	XMLNode getNode(){
		//logic
	}
}


JsonDataProvider{
	JsonContent getContent(){
		// use XMLContent getContent() to get the content
	}
	JSONNode getNode(){
		// use XMLNode getNode() to get the node
	}
}


Main(){

	//new client that operates with JsonDataProvider
	JsonDataProvider jsonDataProvider = new JsonDataProvider();
	JsonContent JsonContent = jsonDataProvider.getContent();
	JSONNode jSONNode = jsonDataProvider.getNode();

}
```
