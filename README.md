# binary-search-by-taking-user-input-
#include <iostream>
using namespace std;
int binarysearch(int arr[],int n,int key){
    int start=0;
    int end=n-1;
    int mid=start+(end-start)/2;
    while(start<=end)
    {
        if (arr[mid]==key)
        {
          return mid;  
        }
        else if( key>arr[mid])//we go to right side of array and ignore left side
        {
            start=mid+1;
        }
        else// ( key<mid)//we go to left side of array and ignore right side
        {
            end=mid-1;
        }
        mid=(start+end)/2;
    }
    return -1;
}

int main()
{
    int n;
    cout<<" enter the size of array"<<endl;
    cin>>n;
    int even[30];
    cout<<" enter the elements of array"<<endl;
    for(int i=0;i<n;i++){
        cout<<" elements"<<i<<" ";
        cin>>even[i];
    }
    
    int key;
    cout<<" enter the element you want to search"<<endl;
    cin>>key;
    int index=binarysearch(even,n,key);
    if(index!=-1){
    cout<<" element found"<<index<<endl;}
    else{
        cout<<" element not found"<<endl;
    }

    return 0;
}
