//# Disjoint-set
//union and find parent functions to find whether two nodes belong to same component of a graph or not 
#include<bits/stdc++.h>
using namespace std;
int rank[10000];
int parent[10000];
void makeset(int n){
    for(int i=0;i<n;i++){
        parent[i]=i;
        rank[i]=0;
    }
}
int  findpar(int n){
    if(parent[n]==n) return n;
    return parent[n]=findpar(parent[n]);
}
void union(int a,int b){
    int x=findpar(a);
    int y=findpar(b);
    if(rank[x]<rank[y]){
        parent[x]=y;
    }
    else if(rank[y]<rank[x]){
        parent[y]=x;
    }
    else {
        parent[x]=y;
        rank[y]++;
            }
}
