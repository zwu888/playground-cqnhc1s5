# 
```C++ runnable
#include <iostream>

const int MAX_SIZE = 100;
using namespace std;

void parenthesis(int pos, int n, int open, int close)
{
    static char str[MAX_SIZE];
    
    if (close == n)
    {
        cout << str << "\n";
    }
    else
    {
        if (open > close) 
        {
            str[pos] = '}';
            parenthesis(pos+1, n, open, close+1);
        }
        if (open < n) 
        {
            str[pos] = '{';
            parenthesis(pos+1,n, open+1, close);
        }
    }
 }
 
 void printParenthesis(int n)
 {
    if (n>0) {
        parenthesis(0,n,0,0);
    }
 }
 
 int main() {
    int n = 5;
    printParenthesis(n);
    cout << endl;
    return 0;
 }
