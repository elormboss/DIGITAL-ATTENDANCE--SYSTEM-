#include <iostream>
#include <fstream>
#include <sstream>
using namespace std;

class Student {
private:
    string indexNumber;
    string name;

public:

    void registerStudent() {
        cout << "Enter Index Number: ";
        cin >> indexNumber;
        cin.ignore();

        cout << "Enter Student Name: ";
        getline(cin, name);

        ofstream file("students.txt", ios::app);

        if(file.is_open()) {
            file << indexNumber << "," << name << endl;
            file.close();
            cout << "Student Registered!\n";
        }
        else {
            cout << "File Error!\n";
        }
    }

    void viewStudents() {
        ifstream file("students.txt");
        string line;

        cout << "\nRegistered Students:\n";

        while(getline(file, line)) {
            stringstream ss(line);
            string index, studentName;

            getline(ss, index, ',');
            getline(ss, studentName);

            cout << "Index: " << index 
                 << " | Name: " << studentName << endl;
        }

        file.close();
    }
};

int main() {

    Student s;
    int choice;

    cout << "1. Register Student\n";
    cout << "2. View Students\n";
    cout << "Enter Choice: ";
    cin >> choice;

    switch(choice) {
        case 1: s.registerStudent(); break;
        case 2: s.viewStudents(); break;
    }

    return 0;
}
