### Subscriber Method-

Is used when a set of Objects need to be notified when a certain set of instructions are done. We have a list of objects which need a notification (called as subscriber)
and haev 2 methods in the Aggregator (subscribe and publish, where the publish method is used to notify the objects).

```
ISubscriber{
	void notify();
}

IEventAggregator{
	subscribe(eventName, subscriber)
	publish()
}

eventAggregrator{
	Map<String, List<Isubscirber>> routeTable;
	subscribe(eventName, subscriber){
		if(routeTable.has(eventName)){
			routeTable.get(eventName).add(subscriber);
		} else {
			routeTable.add(eventName, Array.asList({subscriber}));
		}
	}
	
	publish(eventName){
		if(routeTable.contains(eventName)){
			List<ISubscriber> subList = routeTable.get(eventName);
			for(Subscriber sub: subList){
				sub.notify();
			}
		}
	}
}
```
