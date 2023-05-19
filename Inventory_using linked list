#include<iostream>

using namespace std;
//node class
class Node {
	private:
		string name;
		int id;
		int quantity;
		double price;
		Node *next;

	public:

		//get
		string getName();
		int getId();
		int getQuantity();
		double getPrice();
		Node *getNext();
		//set
		void setName(string name);
		void setId(int id);
		void setQuantity(int quantity);
		void setPrice(double price);
		void setNext(Node *next);

};


//get functions

Node *Node::getNext() {
	return this->next;
}

string Node::getName() {
	return this->name;
}

int Node::getId() {
	return this->id;
}

int Node::getQuantity() {
	return this->quantity;
}
double Node::getPrice() {
	return this->price;
}

//set functions
void Node::setNext(Node *next) {
	this->next = next;
}
void Node::setName(string name) {
	this->name = name;
}
void Node::setId(int id) {
	this->id = id;
}
void Node::setPrice(double price) {
	this->price = price;
}
void Node::setQuantity(int quantity) {
	this->quantity = quantity;
}


//inventory class
class Inventory {
	private:
		Node *head;
	public:
		Inventory();
		void addProduct(string name, int id, int quantity, double price);
		void removeProduct(int id);
		void updateProduct(int id, int quantity, double price);
		void displayInventory();
};

//constructor
Inventory::Inventory() {
	head = NULL;
}

//update product function
void Inventory::updateProduct(int id, int quantity, double price) {
	Node *newNode = head;
	while(newNode != NULL) {
		if(newNode->getId() == id) {
			newNode->setQuantity(quantity);
			newNode->setPrice(price);
			cout << "Product updated in Inventory."<< endl;
			return;
		}
		newNode = newNode->getNext();
	}
}

void Inventory::addProduct(string name, int id, int quantity, double price){
	Node *newNode = new Node;
	newNode->setId(id);
	newNode->setName(name);
	newNode->setPrice(price);
	newNode->setNext(NULL);
	newNode->setQuantity(quantity);
	
	
	if(head == NULL){
		head = newNode;
	}
	else{
		Node *last = head;
		while(last->getNext() != NULL){
			last = last->getNext();
		}
		last->setNext(newNode);
	}
	cout << "Product Added Successfully." << endl;
}

// remove Product function
void Inventory::removeProduct(int id){
	if(head == NULL){
		cout << "Inventory is Empty." << endl;
		return;
	}
	
	if(head->getId() == id){
		Node *temp = head;
		head = head->getNext();
		delete temp;
		
		cout << "Product removed from Inventory." << endl;
		return;
	}
	
	Node* newNode = head;
	while(newNode->getNext() != NULL){
	if(newNode->getNext()->getId() == id){
		Node *temp = newNode->getNext();
		newNode->setNext(newNode->getNext()->getNext());
		delete temp;
		cout << "product removed from Inventory." << endl;
		return;
	}
	newNode = newNode->getNext();
	}//end of while.
	
	cout << "Product not found in Inventory." << endl;
}//end of remove product function


//show function
void show(){
	cout << "Inventory: " << endl;
	cout << "Name" << "\t" << "ID" << "\t" << "Quantity" << "\t" << "Price" << endl;
}

//display Inventory function
void Inventory::displayInventory(){
	if(head == NULL){
		cout << "Inventory is empty." << endl;
		return;
	}
	show();
	Node *newNode = head;
	while(newNode != NULL){
		cout << newNode->getName() << "\t" << newNode->getId() <<"\t" << newNode->getQuantity() << "\t\t" << newNode->getPrice();
		cout << endl;
		newNode = newNode->getNext();
	}//end of while.
}


main() {
Inventory myInventory;
int choice, id, quantity, products;
string name;
double price;

do{
	cout << "Please choose an Action: " << endl;
	cout << "1. Add Product" << endl;
	cout << "2. Remove Product" << endl;
	cout << "3. Update Product" << endl;
	cout << "4. Display Inventory" << endl;
	cout << "0. Exit" << endl;
	
	cout << "Enter your Choice: ";
	cin >> choice;
	
		
	switch(choice){
	case 1:
		cout << "How many products do you want to add?";
		cin >> products;
		
		for(int i = 0; i < products; i++){
			cout << "Enter product name: ";
			cin >> name;
			
			cout << "Enter product ID: ";
			cin >> id;
			
			cout << "Enter product Quantity: ";
			cin >> quantity;
			
			cout << "Enter product Price: ";
			cin >> price;
		myInventory.addProduct(name, id, quantity, price);	
			
		}//end of for loop
		
	break;
	
	case 2:
		cout << "Enter product ID to remove: ";
		cin >> id;
		myInventory.removeProduct(id);
	break;
	
	case 3:
		cout << "Enter product ID to Update: ";
		cin >> id;
		
		cout << "Enter new Quantity: ";
		cin >> quantity;
		
		cout << "Enter new Price: ";
		cin >> price;
		
		myInventory.updateProduct(id, quantity, price);
	break;
	
	case 4:
		myInventory.displayInventory();
	break;
	
	case 0:
		cout << "Exit Program";
	    break;	

}//end of switch statement
cout << endl;
}

while(choice != 0);
return 0;
	
}//end of main function
