class Solution
{
	public:
	//Function to find the shortest distance of all the vertices
    //from the source vertex S.
    vector <int> dijkstra(int V, vector<vector<int>> adj[], int S)
    {
       //initialise a vector with maximum distance
       
       vector<int>distance(V, INT_MAX); 
       
       queue<pair<int,int>>q; 
       
       q.push({S,0}); 
       distance[S] = 0; 
       
       while(!q.empty()){
           
            auto front = q.front(); 
            q.pop(); 
            
            int node = front.first; 
            int dist = front.second ; 
            
            for(auto x: adj[node]){
                
                    int first = x[0]; 
                    int second = x[1]; 
                    
                    if(distance[first]> distance[node]+second){
                        
                        distance[first] = distance[node] +second; 
                            int n =distance[first]; 
                        q.push({first,n}); 
                    }
            }
       }
       
       return distance; 
    }
};
