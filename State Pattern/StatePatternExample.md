### State Pattern-
Context class, can change its state multiple times
So Multiple state classes, showing different patterns are created 

The state class change the state whenever necessary

```
interface IAppliance {
	on()
	off()
}

abstract class IControl{
	IAppliance appliance
	on()
	off()
	setAppliance(){}
}


TV implements Appliance{
	on()
	off()
}


RemoteControl extends IControl{
	on(){
	//button Push
	appliance.on()
	}
	
	off(){
	//button push
	appliance.off()
	}	
}

AlexaControl extends IControl{
	on(){
	//Voice "ON"
	appliance.on()
	}
	
	off(){
	//Voice "OFF"
	appliance.off()
	}	
}
```
