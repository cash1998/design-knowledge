### Memento pattern- 

3 classes- originator, memento and Caretaker. 
The work of the originator class is to save the previous states of the originator class, and it does it using a list, and with the help of the memento class.

```
class Memento{
	//Memento class
	String content;
	
	void setContent(String content){
		this.content = content;
	}
	
	String getContent(){
		return content;
	}
} 

class Textbox{
	//originator class
	String content;
	void onTextChange(String content){
		this.content = content;
	}
	void Print(){
		//print content
	}
	
	Memento saveState(){
		return new Memento(content);
	}
	
	public void getContentFromMemento(Memento memento){
    		state = memento.getContent();
   	}
}


class TextBoxStateSaver{
	//caretaker class
	List<Memento> saveStates;

	TextBoxStateSaver(){
		saveStates = new ArrayList<>();
	}
	void addToSavestates(Textbox tb){
		saveStates.add(tb);
	}
	Textbox getLastSave(){
		return saveState.remove(saveState.size()-1);
	}
} 
```
