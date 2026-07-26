1class Solution {
2public:
3    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
4        int n1=nums1.size();
5        int n2=nums2.size();
6        vector<int>merg(n1+n2);
7        int k=0;
8        for(int i=0; i<n1; i++){
9              merg[k]=nums1[i];
10              k++;
11        }
12        
13        for(int i=0; i<n2; i++){
14            merg[k]=nums2[i];
15            k++;
16        }
17        for(int i=0; i<n1+n2; i++){
18            for(int j=0; j<n1+n2; j++){
19                if(merg[i]>merg[j]){
20                    int temp=merg[i];
21                    merg[i]=merg[j];
22                    merg[j]=temp;
23                }
24            }
25        }
26
27            int n= n1+n2;
28          if(n%2!=0){
29            return merg[n/2];
30          }
31          else{
32            return (merg[n/2-1]+merg[n/2])/2.0;
33          }
34        }
35    
36};