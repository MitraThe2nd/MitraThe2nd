#include <string>       // std::string
#include <iostream>     // std::cout
#include <fstream>
#include <map>
using namespace std;

class purse {
    public:
    string key;
    int money=0;
    void getkey (){
       cin >> key;
    }
};


int main () {
    map <string, purse> mytoken;
    purse tem;
    ifstream in;
    in.open("C:\\token\\token.txt");
    int money;
    string i,s1,s2;
    while (in >> s1 >> s2 >> money){
        tem.money=money;
        tem.key=s2;
        mytoken[s1]=tem;
    }
    cout << "it's my token project" <<endl;
    while (i!="exit") {
        cout << "chose what u want to do" << endl;
        cout << "registration" << endl;
        cout << "login" << endl;
        cout << "look_finance" << endl;
        cout << "exit" << endl;
        cin >> i;
        if (i=="registration") {
            string login;
            purse tem;
            cout << "Ur login - ";
            cin >> login;

            if (mytoken.find(login) == mytoken.end())
            {
                cout << "password - ";
                tem.getkey();
                mytoken[login]=tem;
                cout << "now u need login"<< endl;
            }
            else
                cout << "ur login is bused" << endl;
        }
        if (i=="login") {
            cout << "Ur login - ";
            string login;
            cin >> login;
            if (mytoken.find(login) != mytoken.end()){
                auto currentlogin = mytoken.find(login);
                cout << "password - ";
                string password;
                cin >> password;
                if (password==currentlogin->second.key) {
                    cout <<"entire was succesfull" << endl<< endl;
                    string j;
                    while (j!="exit"){
                        cout << "chose what u want to do" << endl;
                        cout << "veiw" << endl;
                        cout << "buy" << endl;
                        cout << "send" << endl;
                        cout << "exit" << endl;
                        cin >> j;
                        if (j=="veiw") {
                            cout << "U have " << currentlogin->second.money << " my tokens"<<endl;
                        }
                        if (j=="buy"){
                            cout <<"how many u wanna buy" << endl;
                            int k;
                            cin >> k;
                            currentlogin->second.money=currentlogin->second.money+k;
                        }
                        if (j=="send"){
                            cout <<"write name whom u wanna send - ";
                            string name;
                            cin >>name;
                            if (mytoken.find(name) != mytoken.end()){
                                auto whom = mytoken.find(name);
                                cout << "write number of tokens - ";
                                int k;
                                cin >> k;
                               if (currentlogin->second.money-k>=0) {
                                   currentlogin->second.money=currentlogin->second.money-k;
                                   whom->second.money=whom->second.money+k;
                               }
                               else cout << "u havent enought tokens" << endl;
                            }
                            else cout << "cannot be found name" << endl;


                        }

                    }
                }
                else cout <<"wrong password" << endl;
            }
        }
        if (i=="look_finance") {
            for (auto now : mytoken) {
                cout << now.first << " - " << now.second.money << "\n";
                }
        }
    }



    ofstream out("C:\\token\\token.txt");

        if (out.is_open())
        {
            for (auto now : mytoken)
            {
                out << now.first <<" " << now.second.key <<" " << now.second.money << "\n";
            }
        }
        out.close();
    return 0;
}
