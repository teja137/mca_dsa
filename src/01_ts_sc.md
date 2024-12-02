**Space and time complexity**

**Time complexity**

1. Constant Time
Problem: Check if a number is odd.

bool isOdd(int n) {
    return n % 2 != 0;
}

tc: Constant Time: O(1)
Explanation: Only one operation, irrespective of the size of the input.

2. Logarithmic Time
Problem: Binary search in a sorted array.

int binarySearch(int arr[], int n, int target) {
    int left = 0, right = n - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target)
            return mid;
        else if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }
    return -1;
}

tc: Constant Time: O(log n)
Explanation: Halves the search space at each step.

3. Linear Time
Problem: Find the sum of an array.

int sumArray(int arr[], int n) {
    int sum = 0;
    for (int i = 0; i < n; i++) {
        sum += arr[i];
    }
    return sum;
}

tc: Constant Time: O(n)
Explanation: Iterates through all n elements of the array.

4. Linearithmic Time
Problem: Merge sort.

void merge(int arr[], int left, int mid, int right) {
    int n1 = mid - left + 1;
    int n2 = right - mid;
    int L[n1], R[n2];
    for (int i = 0; i < n1; i++) L[i] = arr[left + i];
    for (int j = 0; j < n2; j++) R[j] = arr[mid + 1 + j];
    int i = 0, j = 0, k = left;
    while (i < n1 && j < n2) arr[k++] = (L[i] <= R[j]) ? L[i++] : R[j++];
    while (i < n1) arr[k++] = L[i++];
    while (j < n2) arr[k++] = R[j++];
}

void mergeSort(int arr[], int left, int right) {
    if (left < right) {
        int mid = left + (right - left) / 2;
        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);
        merge(arr, left, mid, right);
    }
}

tc: Constant Time: O(n log n)
Explanation: Divide-and-conquer approach results in O(log n) recursion levels, with O(n)work at each level.

5. Quadratic Time
Problem: Find all pairs in an array.

void findPairs(int arr[], int n) {
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            printf("(%d, %d)\n", arr[i], arr[j]);
        }
    }
}

tc: Constant Time: O(n^2)
Explanation: Two nested loops result in n*n = O(n^2)

6. Exponential Time
Problem: Generate all subsets of a set.

void generateSubsets(char set[], int n) {
    int total = 1 << n; // 2^n subsets
    for (int i = 0; i < total; i++) {
        for (int j = 0; j < n; j++) {
            if (i & (1 << j)) {
                printf("%c", set[j]);
            }
        }
        printf("\n");
    }
}

tc: Constant Time: O(2^n)
Explanation: Generates 2^n subsets for a set of size n.


**Space Complexity**

1.  Constant Space
Problem: Reverse an array in-place.

void reverseArray(int arr[], int n) {
    int start = 0, end = n - 1;
    while (start < end) {
        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        start++;
        end--;
    }
}

tc: Constant Time: O(1)
Explanation: Only a few variables (start, end, temp) are used.

2.Logarithmic Space 
Problem: Calculate the height of a binary tree (recursive).

int height(TreeNode* root) {
    if (root == NULL)
        return 0;
    int leftHeight = height(root->left);
    int rightHeight = height(root->right);
    return 1 + (leftHeight > rightHeight ? leftHeight : rightHeight);
}

tc: Constant Time: O(log n)
Explanation: The recursion stack depth in a balanced binary tree is log n

3. Linear Space
Problem: Store Fibonacci sequence.

void fibonacci(int n) {
    int fib[n];
    fib[0] = 0;
    fib[1] = 1;
    for (int i = 2; i < n; i++) {
        fib[i] = fib[i - 1] + fib[i - 2];
    }
    for (int i = 0; i < n; i++) {
        printf("%d ", fib[i]);
    }
}

tc: Constant Time: O(n)
Explanation: Uses an array of size n to store Fibonacci numbers.

4. Linearithmic Space
Problem: Merge sort (in-place modification requires additional log levels).

tc: Constant Time: O(n log n)
Explanation: Recursive calls and temporary arrays contribute to O(n log n)

5. Quadratic Space
Problem: Dynamic programming 2D table.

int lcs(char* X, char* Y, int m, int n) {
    int dp[m + 1][n + 1];
    for (int i = 0; i <= m; i++) {
        for (int j = 0; j <= n; j++) {
            if (i == 0 || j == 0)
                dp[i][j] = 0;
            else if (X[i - 1] == Y[j - 1])
                dp[i][j] = 1 + dp[i - 1][j - 1];
            else
                dp[i][j] = (dp[i - 1][j] > dp[i][j - 1]) ? dp[i - 1][j] : dp[i][j - 1];
        }
    }
    return dp[m][n];
}

tc: Constant Time: O(n^2)
Explanation: A 2D table of size m×n.

6. Exponential Space
Problem: Recursive Fibonacci with recursion depth.

int fibonacci(int n) {
    if (n <= 1)
        return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

tc: Constant Time: O(2^n)
Explanation: Recursion stack depth doubles at each level, resulting in 2^n calls.