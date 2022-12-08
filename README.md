# CTSL-LIBRARY
//Dr_T Unit 2 COSC-1437 Starter 
/* Task -

Top level solution folder: C_STL_Library_YourLastName
//Credit https://www.geeksforgeeks.org/passing-vector-constructor-c/ clarifications added
create a single main.cpp that contains code samples and implementations of each of the following topics */
#include <set>
#include <iostream>
#include <vector>
#include <algorithm> 
#include <string>
#include <stack>
#include <cassert>
#include <utility>
#include<map>
using namespace std; 
typedef map<string, int> MapT; // MapT prototype
typedef MapT::const_iterator MapIterT;
//VECTOR TO CLASS MEMBER FUNCTIONS


class MyClassVector1 
{ 
  private:  
      vector<int> veci;


  public: 
      MyClassVector1 (vector<int> vi)  
{ 
        veci = vi; 
      } 
      void printvi() 
      { 
          for (int i = 0; i < veci.size(); i++) 
          {
              cout << veci[i] << " "; 
          }    
      }
};
class MyClassVector2
{ 
  private:  
      vector<double> vecd;

public: 
  MyClassVector2 (vector<double> vd)  
{ 
        vecd = vd; 
      } 
      void printvd() 
      { 
          
          for (int i = 0; i < vecd.size(); i++) 
          {
              cout << vecd[i] << " "; 
          }    
      } 
};
class MyClassVector3
{ 
  private:  
      vector<string> vecs;

public: 
  MyClassVector3 (vector<string> vs)  
{ 
        vecs = vs; 
      } 
      void printvs() 
      { 
         
          for (int i = 0; i < vecs.size(); i++) 
          {
              cout << vecs[i] << " "; 
          }    
      } 
};
int main() 
{
  //VECTORS AND THEIR VALUES

  
    vector<double> vd; 
    vector<int> vi; 
    vector<string> vs; 


   
   
    vd.push_back(2.89);
    vd.push_back(3.24);
    vd.push_back(55.4); 

 vi.push_back(5);
    vi.push_back(4);
    vi.push_back(7);
    
  
 
vs.push_back("What is love??");
  vs.push_back("hello");
  vs.push_back("bye");
   
   cout << "\nValues in vd: \n"; 
   for(double vals : vd)
   {
     cout << vals << endl; 
   }
   cout << "\nAnother way to print vector: " << endl; 
   for(int i = 0; i < vd.size(); i++)
   {
     cout << vd[i] << endl; 
   }

   

   cout << "\nVI components: " << endl; 
   for(int i = 0; i < vi.size(); i++)
   {
     cout << vi[i] << endl; 
   }

   cout << "\nVS components: " << endl; 
   for(int i = 0; i < vs.size(); i++)
   {
     cout << vs[i] << endl; 
   }


    /****Section_Name***Vector_as_Class_Member*/ 
    //Credit https://www.geeksforgeeks.org/passing-vector-constructor-c/

   cout << "\nVectorINT as Class Member" << endl; 
   
        
        MyClassVector1 obji(vi); 
       obji.printvi();
           
      cout << "\nVectorDOUBLE as Class Member" << endl; 
   
      
        MyClassVector2 objd(vd); 
       objd.printvd();

    cout << "\nVectorSTRING as Class Member" << endl; 
   
      
        MyClassVector3 objs(vs); 
       objs.printvs();
            
     cout << endl<<endl << "Values of VINT: ";

    /****Section_Name***STL_Iterators*/ 
    vector<int> vint(10);
vint[0]= 10, vint[1]= 12, vint[2]= 11,vint[3]= 115,vint[4]= 123,
  vint[5]= 14,vint[6]= 15,vint[7]= 16,vint[8]= 17,vint[9]= 19;

  vector<int> ::iterator it;
  for (it = vint.begin(); it != vint.end(); ++it){
    cout << " " << *it;
  }
    /****Section_Name*** Stack*/
stack<int> st;
  st.push (100); //put 100 in stack
  assert(st.size() == 1); //verify only one stack
  assert(st.top()== 100); //verify value

st.top() = 456;
assert(st.top()== 456);

st.pop(); //deletes elements
assert (st.empty() == true);  

  

    /****Section_Name**** Set*/
    //Write the code as presented in: 3. std::set
cout << endl << endl << "SET FUNCTIONS: ";
set <int> iset;
  iset.insert(11); // insert the values into the set
  iset.insert(-11);
iset.insert(55);  
iset.insert(22);
  iset.insert(22);
  if(iset.find(55) != iset.end()){ // is the value stored
    iset.insert(55);
  }
  assert(iset.size() == 4); // checking size
    set <int> ::iterator itt;
  for (itt = iset.begin(); itt != iset.end(); itt++){ // output values
    cout << " " << *itt;
  }


    /****Section_Name****Pair_Structure*/
    //Write the code as presented in: 4. std::pair structure
pair <string , string> strstr;
  strstr.first= "Hello";
  strstr.second= "World"; // pairing 2 strings "Hello" and "World"

  pair <int , string> intstr;
  intstr.first= 1;
  intstr.second= "One"; // pairing 1 string and 1 int "1" and "one"

  pair <string , int > stringint("Two", 2) ; // predefined values
  assert(stringint.first == "Two");
  assert(stringint.second = 1); //checking values
  
  
  
 

    /****Section_Name**** Map_Insert*/
    //Write the code as presented in: 14. std::map::insert
MapT amap; // call Map T function as amap
  pair <MapIterT, bool> result= 
  amap.insert(make_pair("Fred", 45)); // insert these values to the map

  assert(result.second == true);
  assert(result.first->second== 45); //check values

  result = amap.insert(make_pair("Fred", 54)); //insert new values

  assert(result.second == false);
assert(result.first->second == 45); // back to old value
  

    /****Section_Name****Map_Summary*/
    //Write the code as presented in: 16. Map summary
cout << endl <<  endl << "MAP SUMMARY: ";
  
map<string, string> phonebook;
  phonebook["411"] = "directory";
  phonebook["911"] = "emergency";
  phonebook["508-678-3795"] = "BCC"; //these values in phonebook map will give these 3 outputs

  if(phonebook.find("411") != phonebook.end()){
    phonebook.insert(make_pair( string("411"), string("directory")));
  }; // plugging directory in the mpa if it is not already in it
  assert(phonebook.size()== 3); //making sure the map is 3 maps big
  map<string, string>  ::const_iterator id;
  for( id = phonebook.begin(); id != phonebook.end(); ++id){
    cout << " " << id-> first
      << " " << id-> second << endl;
  }


    /****Section_Name**** Sort_Algorithm*/
    //Write the code as presented in: 23. sort example
  cout << endl << endl;
int arr[100];
  sort (arr, arr+100);

  vector<int> v1;
  sort(v1.begin(), v1.end());


    /****Section_Name****Predicate_Algorithm*/
    //Write the code as presented in: 25. count_if and predicate function
// bool less_than_7(int value){
//   return value < 7 
// }
//   vector<int> v2;
//   int count_less = count_if(v2.begin(), v2.end(), less_than_7);
  //ISSUE RUNNING CODE!!!
      return 0; 
 }
