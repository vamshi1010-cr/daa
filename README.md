// Online C++ compiler to run C++ program online
#include<iostream>
#include<vector>
#include <algorithm>

using namespace std;

int main()
{
    int n;
    cout<<"enter the no. of activities: ";
    cin>>n;
    vector<pair<int,int>> points(n);
    for(int i=0;i<n;i++){
        cin>>points[i].first>>points[i].second;
   }
   sort(points.begin(), points.end(), [](auto &p1, auto &p2) {
        return p1.second < p2.second;
    });

        vector<pair<int,int>> selected;
        int lastFinishedTime = -1;
        for(auto &act: points){
            if(act.first>=lastFinishedTime){
                selected.push_back(act);
                lastFinishedTime=act.second;
            }
        }

        cout<<"selected activities (start,finish): \n";
        for(auto &act: selected){
            cout<<"("<<act.first<<","<<act.second<<")";
        }
        return 0;
}
 # daa
