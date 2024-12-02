void LinearSearch(array, target){
    for i = 0 to length(array) - 1:
        if array[i] == target:
            return i  // Target found at index i
    return -1  // Target not found
}

void BinarySearch(array, target){
    left = 0
    right = length(array) - 1

    while left <= right:
        mid = (left + right) / 2
        if array[mid] == target:
            return mid  // Target found at index mid
        else if array[mid] < target:
            left = mid + 1  // Search in the right half
        else:
            right = mid - 1  // Search in the left half

    return -1  // Target not found
}