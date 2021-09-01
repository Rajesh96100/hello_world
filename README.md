# hello_world
hi friends

//wood cutting made easy
code//
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int binary_search(vector<int> arr,int a,int b,int key)
{
 int ans;
    while(a<=b)
    {
        int mid=a+(b-a)/2;
        int x =0;
        for(int i=0;i<arr.size();i++)
        {
            if(arr[i]-mid>0)
            {
                x=x+arr[i]-mid;
                if(x>key)
                {
                    break;
                }
            }
        }
       if(x>key)
        {
            a=mid+1;
            ans = max(ans,mid);
        }
        else
        {
            b=mid-1;
        }
    }
        return ans;
}
int main()
{
    vector<int> arr;
    arr.push_back(114);
    arr.push_back(55);
    arr.push_back(95);
    arr.push_back(131);
    arr.push_back(77);
    arr.push_back(111);
    arr.push_back(141);

    int result=solve(arr,95);
    cout<<result<<endl;
}
int solve(vector<int> &A, int B) {
    int key=B;
    int min =0;
    int max =A[0];
    for(int i = 1; i < A.size(); i++)
    {
       if(A[i] > max)
       {
           max = A[i];
       }
    }
    int solution=binary_search(A,min,max,key);
    cout<<solution<<endl;
}
