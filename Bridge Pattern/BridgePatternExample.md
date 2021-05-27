### Bridge Pattern- 
Bridge is used when we need to decouple an abstraction from its implementation so that the two can vary independently. This type of design pattern comes under structural pattern as this pattern decouples implementation class and abstract class by providing a bridge structure between them.
Loosly based on the repo that I worked on- 
```
public abstract class BaseTransformer{
	List<BasePredicate> predicates;
	void transform();
	void createMessage();
}

public interface BasePredicate{
	boolean apply();	
}

public class ChronicPredicate implements BasePRedicate{
	boolean apply(){
		//return true/false;
	}
}

public class GIPredicate implements BasePRedicate{
	boolean apply(){
		//return true/false;
	}
}


public class GIAdvance extends BaseTransformer{
	void transform(){
		for (predicate: predicates){
			if(predicate.apply()){
				//do some operation
			}
		}
	}

	void createMessage(){
		//create messages
	}
}
```
