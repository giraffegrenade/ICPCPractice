# ICPCPractice

## Data Structures

### Fenwick Tree / Binary Search Tree

Used to perform range sum queries with updates and queries in O(log n) time.

### Segment Tree

Similar to BST but supports a larger range of queries such as sum, minimum, maximum, and others, all in O(log n) time.

### K-D Tree

?

### Union-find / Disjoint Set

Data structure that keeps track of a set of elements partitioned into a number of disjoint (non-overlapping) subsets.

A union-find algorithm is an algorithm that performs two useful operations on such a data structure:

Find: Determine which subset a particular element is in. This can be used for determining if two elements are in the same subset.

Union: Join two subsets into a single subset.

```cpp
struct UnionFindSet {
	vector<int> parent;
	void init(int nn) {
		parent.resize(nn + 1);
		for (int i = 0; i < parent.size(); i++)
			parent[i] = i;
	}

	void merge(int x, int y) {
		parent[find(x)] = find(y);
	}
	int find(int x) {
		return x == parent[x] ? x : parent[x] = find(parent[x]);
	}
	bool together(int x, int y) {
		return find(x) == find(y);
	}
};
```
