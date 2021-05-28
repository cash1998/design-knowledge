### Facade Pattern

Facade pattern hides the complexities of the system and provides an interface to the client using which the client can access the system. This type of design pattern comes under structural pattern as this pattern adds an interface to existing system to hide its complexities.

Another example of a pattern used in our repo. We used the CucumberTest to run our unit tests.
```
class TestExecuter{
	parseFile(File filepath){
		//parse the file, get the input elements, using Given, when, then
		//return the filePath
	}
	
	convertToJson(filepath){
		//convert the file details from string to json
	}
	
	assertThejsonANdResult(){
		//assert
	}
	
	
}

class CucumberTest{
	TestExecuter testExecuter;
	CucumberTest(){
		testExecuter = new TestExecuter();
	}
	
	boolean runCucumberTest(){
		String filepath = testExecuter.parseFile(path);
		String jsonResult = testExecuter.convertToJson(filepath);
		return assertThejsonAndResult(jsonResult);
	}
}


main(){
	CucumberTest cucumberTest = new CucumberTest();
	cucumberTest.runCucumberTest();
}
```
