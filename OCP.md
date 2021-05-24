#### SRP- Single responsibility principle
Every class/function should have a single responsibility,since the more responsibility a class has, it'll have to be changed/edit more often.

#### The battery example-- 
Instead of having a single function, we could've separated it into 3 different functions.
so that the peice of code is independent of each other, and it effectively increases the coverage of the function as well.


#### Dependency Injection- 
"Program for interface, not for implementation"
IoC- Inversion of Control- 

Setter injection- can change the object when needed
Constructor- dependency stated at the start of the initialization, it will not change throughout the lifetime of the object

Strategy Pattern- separate and abstract
		- used a lot
		- is there in a lot of other patterns as well.
		
YAGNI principle- You arent gonna need it

OCP- Open close principle

Abstraction and responsibility segregation are important

###### Example-
```
public interface IpatientSearch {
	PatientRepository patientRepository;
	public void setPatientRespository(PatientRepository patientRepository);
	public PatientData patientSearch(String value);
} 

public class PatientNameSearch implements IpatientSearch{

	PatientRepository patientRepository;
	public void setPatientRespository(PatientRepository patientRepository){
		this.patientRepository = patientRepository;
	}

	public Patientdata patientSearch(String name){
		//search by name
	}
}

public class PatientMRNSearch implements IpatientSearch{

	PatientRepository patientRepository;
	public void setPatientRespository(PatientRepository patientRepository){
		this.patientRepository = patientRepository;
	}

	public Patientdata patientSearch(String MRN{
		//search by MRN
	}
}
```

Composite design pattern - Read on this
Graph uses composite pattern example, can use this

--Design for uniformity, design for type safety 
