# Fsw-dsa
Data Structures and algorithms
 Data Types
   Primitive
     .Int,float,char
      Non Primitive 
         linear   Nonlinear
  Linear:Array,Stack,Qeue,lists
  Nonlinear:tree,graph
Array:Can be acessed randomly
Stack:Follow LIFO(last in first out) cannot be acessed randomly

Main Operations in DSA
Insertion:push()
Deletion:pop()
Updation:
Searching:
Sorting:
Qeue:Follow the FIFO(First in first out)
  here for insertion we have enqeue and for deletion we have deqeue
List:
Single Linked list
     value,address
Double Linked List
   address,value,address(can travel in both direction)

Single Circular Linked List
    Same as the single LL instead of null address in the end we have the address of the head and vice versa
Double Circular Linked List 
    Same as the double LL instead of null address in the end we have the address of the head and vice versa
Sorting
1.Heap Sort  
  >>Max Heap
  >>Min Heap
2.Quick Sort
>With the comparicon of pivot element with each element the swaping is carried out
3.Insertion Sort
>here sorted part is compared with unsoreted part
4.Merge sort
>Divide until we get single element and then conquer to sort
5.Bubble Sort
>Comparing a single element with all the elements at a time

Array and Vectors in C++
eg:
  #include <iostream>
using namespace std;

int main() {
    int numbers[2][3];
    cout<<"Enter 6 numbers"<<endl;
    for(int i=0;i<2;i++){
    for(int j=0;j<3;j++){
        cin>>numbers[i][j];
    }
    }
    cout<<"The numbers are"<<endl;
    for(int i=0;i<2;i++){
    for(int j=0;j<3;j++){
        cout<< "numbers["<<i<<"]["<<j<<"]"<<numbers[i][j]<<endl;
    }
    }
    return 0;
}
Selection sort
#include <iostream>

int main() {
 void selecionsort(int arr[],int n)
  {
     int i,j,min_index;
     for(i=0;i<n-1;i++)
     {
         min_index=i;
        for(j=i+1,j<n;j++)
        {
            if(arr[j]<arr[min_idx])
             min_idx=j;
        }
        swap(&arr[min_idx],&arr[i]);
     }
 }
}
Bubble sort
#include <iostream>

int main() {
 void bubble(int arr[],int n)
  {
     int i,j;
     for(i=0;i<n-1;i++)
     {
        for(j=0,j<n-i-1;j++)
        {
            if(arr[j]>arr[j+1])
           
        swap(&arr[j],&arr[j+1]);
        }
     }
 }
}
Optimised approach
#include <iostream>

int main() {
 void bubble(int arr[],int n)
  {
     int i,j;
     bool swap
     for(i=0;i<n-1;i++)
     {
         swap=false;
        for(j=0,j<n-i-1;j++)
        {
            if(arr[j]>arr[j+1])
            {
            swap(&arr[j],&arr[j+1]);
            swap=true;
            }
     } 
     if(swap==false)
     break;
 }
}
Insertion Sort
#include <iostream>

int main() {
 void insertionsort(int arr[],int n)
  {
     int i,key,j;
     for(i=0;i<n;i++)
     {
        key=arr[i];
        j=i-1;
        while(j>=0&&arr[j]>key)
        {
            arr[j+1]=arr[j];
            j=j-1;
            }
            arr[j+1]=key;
     } 

     Linear Searching
     #include <iostream>
using namespace std;
int main() {
    int arr[10],i,index,num;
    cout<<"Enter 10 numbers";
    for(i=0;i<10;i++)
    cin>>arr[i];
    cout<<"\nEnter the number to search";
    cin>>num;
    for(i=0;i<10;i++)
    {
        if(arr[i]==num)
        {
            index=i;
             cout<<"Number found"<<index;
             cout<<endl;
            break;
            }
            else{
                cout<<"number not found"<<endl;
                break;
            }
    }
    return 0;
}

 }
}
Binary Search
#include <iostream>
using namespace std;

int binarySearch(int a[],int first,int last,int search_num){
        int middle;
        if(last>=first){
            middle=(first+last)/2;
            if(a[middle]==search_num){
                return middle+1;
            }
            else if(a[middle]<search_num){
                return binarySearch(a,middle+1,last,search_num);
            }
            else if(a[middle]>search_num){
                return binarySearch(a,first,middle+1,search_num);
            }
        }
        return -1;
    }
}
Trivailing Zero
#include <iostream>
using namespace std;

int main(){
    int n;
    cin>>n;
    int no_of_zero=0;
    while(n!=0){
        n=n/5;
        no_of_zero=no_of_zero+n;
    }
    cout<<" No of trivailing zeroes:"<<no_of_zero;
    return 0;
}
Two sum
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n,sum;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++){
        cin>>a[i];
    }
    cin>>sum;
    sort(a,a+n);
    int l=0,h=n-1;
    while(l<h){
        if(a[l]+a[h]==sum){
            cout<<a[l]<<" "<<a[h];
            break;
        }
        else{
            if(a[l]+a[h]>sum) h--;
            else l++;
        }
    }
  return 0;  
}
Triplet sum
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++){
        cin>>a[i];
    }
    int sum;
    cin>>sum;
    sort(a,a+n);
    int flag=0;
    for(int i=0;i<n-2&&flag==0;i++){
    int l=i+1;
    int h=n-1;
    while(l<h){
        if(a[i]+a[l]+a[h]<sum) l--;
        else if(a[i]+a[l]+a[h]>sum) h--;
        else{
            cout<<a[i]<<" "<<a[l]<<" "<<a[h];
            flag=1;
            break;
            
        }
    }
}
if(flag==0){
    cout<<"no triplet found"<<endl;
}
    return 0;
}
Move zero to the end of the array optmized version other than brute force
#include <bits/stdc++.h>
using namespace std;
int main() {
    int n;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++){
    cin>>a[i];
    }
    int count=0;
    for(int i=0;i<n;i++)
    {
        if(a[i]!=0)
           {
            a[count]=a[i];
            count++;
            }
    }
    while(count<n){
        a[count]=0;
        count++;
    }
    for(int i=0;i<n;i++){
    cout<<a[i]<<"";
    }
    cout<<endl;
    return 0;
}
Zero Sum
#include <bits/stdc++.h>
using namespace std;
int main() {
    int n;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++){
    cin>>a[i];
    }
    unordered_map<int,int>mp;
    int sum=0,find_sub=0;
    for(int i=0;i<n;i++){
        sum=sum+a[i];
        if(sum==0){
            find_sub=1;
        }
        else{
            if(mp[sum]>0){
                find_sub=1;
            }
            else{
                mp[sum]++;
            }
        }
    }
    if(find_sub==1){
        cout<<"true"<<endl;
    }
    else{
         cout<<"false"<<endl;
    }
    return 0;
}
Equilibrium index
#include <bits/stdc++.h>
using namespace std;
int main() {
    int n;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++)
    {
        cin>>a[i];
    }
    int totalsum=0;
    for(int i=0;i<n;i++)
    {
         totalsum=totalsum+a[i];
    }
    int lhssum=0,flag=0;
    for(int i=0;i<n;i++)
    {
        totalsum=totalsum-a[i];
        if(lhssum==totalsum){
            cout<<i<<endl;
            flag=1;
            break;
        }
        else{
            lhssum=lhssum+a[i];
        }
    }
    if(flag==0){
        cout<<-1<<endl;
    }
    return 0;
}
