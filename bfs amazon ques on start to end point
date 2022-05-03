#include <bits/stdc++.h>
using namespace std;
bool isvalid(int i,int j,int n,int m,vector<vector<int>>&mat)
{
    if(i<0 or j<0 or i>=n or j>=m or mat[i][j]==0)return false;
    return true;
}
int bfs(int n,int m,vector<vector<int>>&mat)
{
    //vector<vector<int>>vis(n,vector<int>(m,0));
    vector<vector<int>>vis(n,vector<int>(m,0));
    vis[0][0]=1;
    int di[4]={-1,0,1,0};
    int dj[4]={0,1,0,-1};
    queue<pair<pair<int,int>,int>>q;
    q.push({{0,0},0});
    if(mat[0][0]==0)return -1;
    if(mat[0][0]==9)return 0;
    while(!q.empty())
    {
        auto it=q.front();
        int i=it.first.first;
        int j=it.first.second;
        int steps=it.second;
        q.pop();
        for(int k=0;k<4;k++)
        {
            int newi=i+di[k];
            int newj=j+dj[k];
            if(isvalid(newi,newj,n,m,mat) and !vis[newi][newj])
            {
                if(mat[newi][newj]==9)
                {
                    return steps+1;
                }
                else
                {
                    q.push({{newi,newj},steps+1});
                    vis[newi][newj]=1;
                }
            }
        }
    }
    return -1;
}
int main()
{
    int n,m;
    cin>>n>>m;
    vector<vector<int>>mat(n,vector<int>(m,0));
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<m;j++)
        {
            cin>>mat[i][j];
        }
    }
    cout<<bfs(n,m,mat);
}
