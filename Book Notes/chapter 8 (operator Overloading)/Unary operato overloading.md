## Operator Overloading
### what it does mean ?

* giving the normal C++ operators,such as +, *, <=, and +=, additional meanings when they are applied to user-defined data types.

---
## Overloading Unary Operators
### Notes :

* when i set 'int' in argument in the defination of operator it dose mean make **Postfix** version of the
operator <br> 
```c++ 
 void operator ++ (int) { cnt++; } //postfix 
 void operator ++ (){++cnt ;}  //prefix
```

---

### Syntax :
`` returnType 'operator' operator (){ body function } ``
---

### example :
```c++
class Counter
{
    private:
        unsigned int count; //count
    public:
        Counter(int cnt = 0) : count(cnt) //constructor
        { }
        unsigned int get_count() //return count
        { return count; }
        Counter operator ++ () //increment count
        {
            ++count;
           return Counter(count);
        }
};
////////////////////////////////////////////////////////////////
int main()
{
    Counter c1, c2; //c1=0, c2=0
    cout << “\nc1=” << c1.get_count(); //display
    cout << “\nc2=” << c2.get_count();
    ++c1; //c1=1
    c2 = ++c1; //c1=2, c2=2
    cout << “\nc1=” << c1.get_count(); //display again
    cout << “\nc2=” << c2.get_count() << endl;
    return 0;
}
```



