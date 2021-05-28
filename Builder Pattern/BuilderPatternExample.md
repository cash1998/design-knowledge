### Builder Pattern

Builder pattern builds a complex object using simple objects and using a step by step approach. This type of design pattern comes under creational pattern as this pattern provides one of the best ways to create an object.
```
interface Walls{
	void createWalls();
}

interface Floors{
	void createFloors();
}


interface Roof{
	void createRoof();
}


class ApartmentRoof implements Roof{
	void createRoof(){
		//logic for apartment roof
	}
}


class ApartmentFloors implements Floors{
	void createFloors(){
		//logic for apartment floors
	}
}


class ApartmentWalls implements Walls{
	void createWalls(){
		//logic for apartment walls
	}
}


class BungalowRoof implements roof{
	void createRoof(){
		//logic for Bungalow roof
	}
}


class BungalowFloors implements floors{
	void createFloors(){
		//logic for Bungalow floors
	}
}


class BungalowWalls implements walls{
	void createWalls(){
		//logic for Bungalow walls
	}
}


class HouseBuilder{
	Walls walls;
	Floors floors;
	Roof roof;
	
	void createBungalow(){
		walls = new BungalowWalls();
		floors = new BungalowFloors();
		roof = new BungalowRoof();
		walls.createWalls();
		roof.createRoof();
		floors.createFloors();
	}
	
	void createApartment(){
		walls = new ApartmentWalls();
		floors = new ApartmentFloors();
		roof = new ApartmentRoof();
		walls.createWalls();
		roof.createRoof();
		floors.createFloors();
	}
}
```


main(){
	HOuseBuilder houseBuilder = new HouseBuilder();
	houseBuilder.createBungalow();
	houseBuilder.createApartment();
}
