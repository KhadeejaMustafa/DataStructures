#include<iostream>
using namespace std;
//Node class
class Node {
	private:
		int data;
		Node *nextNode;

	public:
		void set(int value) {
			data = value;
		}
		int get() {
			return data;
		}
		void setNext(Node *next) {
			nextNode = next;
		}
		Node *getNext() {
			return nextNode;
		}
};
//List class
class List {
	private:
		Node *headNode;
		Node *currentNode;
		Node *lastCurrentNode;
	public:
		//constructor
		List() {
			headNode = NULL;
			currentNode = NULL;
			lastCurrentNode = NULL;
		}
		Node *get() {
			return headNode;
		}
		//add function
		void add(int value) {
			Node *newNode = new Node();
			newNode->set(value);
			newNode->setNext(NULL);

			if(headNode == NULL) {
				headNode = newNode;
				lastCurrentNode = newNode;
			} else {
				lastCurrentNode->setNext(newNode);
				lastCurrentNode = newNode;
			}
		}//end of add function

		//next function
		void next() {
			if(currentNode == NULL) {
				currentNode = headNode;
			} else {
				currentNode = currentNode->getNext();
			}
		}//end of next function.

		//declaring friend functions of the class
		friend void traverse(List list);
		friend List addNodes();
		friend List mergeLists(List oddList, List evenList);
};

//traverse function
void traverse(List list) {
	Node *current = list.headNode;
	while(current != NULL) {
		cout << "List Element: " << current->get() << endl;
		current = current->getNext();
	}
	cout << endl;
}
//addNodes function
List addNodes() {

	List list;
	int input;

	for (int i = 0; i < 9; ++i) {
		cout << "Enter NUMERIC characters of your VU ID: " <<endl;
		cin >> input;
		list.add(input);
	}
	return list;
}

//mergeLists function
List mergeLists(List oddList, List evenList) {
	List mergedList;
	Node *currentOddValue = oddList.get();
	Node *currentEvenValue = evenList.get();

	while(currentOddValue != NULL) {
		mergedList.add(currentOddValue->get());
		currentOddValue = currentOddValue->getNext();
	}

	while(currentEvenValue != NULL) {
		mergedList.add(currentEvenValue->get());
		currentEvenValue = currentEvenValue->getNext();
	}
	return mergedList;
} //end of function.

main() {
	List myList = addNodes();
	List oddList;
	List evenList;
	int digit;

	Node *current = myList.get();

	while(current != NULL) {
		digit = current->get();

		if(digit % 2 == 0) {
			evenList.add(digit);
		} else {
			oddList.add(digit);
		}

		current = current->getNext();
	}
	cout<<"\n ************ OUTPUT ************" << endl;

	//printing odd list
	cout << "\nOdd List: " << endl;
	traverse(oddList);

	//printing even list
	cout << "\nEven List: " << endl;
	traverse(evenList);

	//merging the odd and even lists
	List mergedList =  mergeLists(oddList,evenList);
	cout << "\nMerged List: " <<endl;
	traverse(mergedList);

	return 0;

}//end of main function
