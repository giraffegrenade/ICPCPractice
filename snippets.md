#### Initialising 2D Vector

vector<vector<int>> dp (i+1,vector <int> (j+1, -1));

#### Dijkstra's

#include <iostream>
#include <vector>
#include <queue>
#include <stdlib.h>
#include <limits>
using namespace std;
    
```cpp
const int INF = numeric_limits<int>::max();
```

```cpp
int main() {
    int n;
    cin >> n;
    vector<pair<int, int>> G[n];
    vector<int> numItems (n);
    for (int i=0; i<n; i++) {
        cin >> numItems[0];
    }
    int m;
    cin >> m;
    for (int i=0; i<m; i++) {
        int a, b, w;
        cin >> a >> b >> w;
        G[a-1].push_back({b-1, w});
    }


    vector<int> distance(n);
    // vector<int> items(n);
    vector<int> processed(n);
    std::priority_queue<pair<int, int>> q;
    int x = 0;

    for (int i = 1; i < n; i++) distance[i] = INF;
    distance[x] = 0;
    q.push({0,x});
    while (!q.empty()) {
        int a = q.top().second; q.pop();
        if (processed[a]) continue;
        processed[a] = true;
        for (auto u : G[a]) {
            int b = u.first, w = u.second;
            if (distance[a]+w < distance[b]) {
                distance[b] = distance[a]+w;
                q.push({-distance[b],b});
            }
        }
    }
    
    for (auto x : distance) {
        cout << x << " ";
    }
    
    return 0;
}
```
