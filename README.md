# C-Binary-Search
BInary Search in C++

#include <bits/stdc++.h>
using namespace std;

int binarySearch(int arr[], int key, int left , int right)
{
    if(left<=right){
        int midValue=left + (right-1)/2;
        if(arr[midValue]==key){
            return midValue;
        }
        if(arr[midValue]<key){
            return binarySearch(arr,key,midValue+1,right);
        }
        return binarySearch(arr, key, left,midValue-1);
    }
    return -1;
}
int main(){
    int size,key;
    cout<<"Enter size of array: ";
    cin>>size;
    
    int arr[size];
    cout<<"Enter elements of array(sorted array): ";
    for(int i=0;i<size;++i){
        cin>>arr[i];
    }
    cout<<"Enter key: ";
    cin>>key;
    cout<<binarySearch(arr,key,0,size-1);
    return 0;
}
