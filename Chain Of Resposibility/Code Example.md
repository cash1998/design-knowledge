#### Chain of resposibility- 
this (usually) has a reference to itself, and using that, we can create a chain (since every class that extends/implements it will have a reference to it as well). Useful when chain of processes is needed to be created.

##### Example-
```
//This class has an instance of itself. It can be 
//used to execute the "next step"
abstract class Process {
	Process process;
	void setProcess(Process process){
		this.process = process;
	}
	void execute();
} 
 

class StepX extends Process {
	void execute(){
		//some X logic
		process.execute();
	}
}


class StepY extends Process {
	void execute(){
		//some Y logic
		process.execute();
	}
}


class StepZ extends Process {
	void execute(){
		//some Z logic
		process.execute();
	}
}


main(){
	Process firstStep = new StepZ();
	Process secondStep = new StepX();
	Process thridStep = new StepY();
	
	firstStep.setProcess(secondStep);
	secondStep.setProcess(thridStep); 
	
  //executing this will in turn execute the execute function of 
  //secondStep and thirdStep as well
	firstStep.execute();
}
```
