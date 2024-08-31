#include <iostream>
#include <fstream>
#include <string>

using namespace std;

int main(int argc, char **argv) {
    if (argc < 2) {
        cerr << "ERROR: Not enough command line arguments" << endl;
        return 1;
    }
    const string filename = argv[1];
    
    
    ifstream infile(filename);
    if (!infile.is_open()) {
        cerr << "ERROR: Could not open file " << filename << endl;
        return 1;
    }
    string last_name;
    string first_name;
    double balance;
    int account_no;

    cout << "Current contents of file:" << endl << endl;

    
    while (infile >> last_name >> first_name >> account_no >> balance) {
        cout << "Name: " << first_name << " " << last_name << " (" << account_no << ")" << endl;
        cout << "Balance: " << balance << endl << endl;
    }
    
    // Close the file
    infile.close();

    return 0;
}
