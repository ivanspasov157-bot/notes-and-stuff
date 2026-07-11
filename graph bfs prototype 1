graph bfs prototype 1 (it works on the whole graph, i need to make it so it takes input for beggining and end)

// BFS for one connected component
function bfsConnected(adj, src, visited, res) {
    const queue = [];

    visited[src] = true;
    queue.push(src);

    while (queue.length > 0) {
        const current = queue.shift();
        res.push(current);

        for (const neighbor of adj[current]) {
            if (!visited[neighbor]) {
                visited[neighbor] = true;
                queue.push(neighbor);
            }
        }
    }
}

// BFS for the entire graph, including disconnected components
function bfs(adj) {
    const vertexCount = adj.length;
    const visited = new Array(vertexCount).fill(false);
    const result = [];

    for (let i = 0; i < vertexCount; i++) {
        if (!visited[i]) {
            bfsConnected(adj, i, visited, result);
        }
    }

    return result;
}

function addEdge(adj, u, v) {
    adj[u].push(v);
    adj[v].push(u);
}

// Create adjacency list
const vertexCount = 6;
const adj = [];

for (let i = 0; i < vertexCount; i++) {
    adj.push([]);
}

addEdge(adj, 1, 2);
addEdge(adj, 2, 0);
addEdge(adj, 0, 3);
addEdge(adj, 4, 5);

const result = bfs(adj);

console.log(result);
