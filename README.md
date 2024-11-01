import random
import time
def quick(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quick(arr, low, pi - 1)
        quickt(arr, pi + 1, high)
def partition(arr, low, high):
    pivot = arr[high]
    i = (low - 1)
    for j in range(low, high):
        if arr[j] <= pivot:
            i = i + 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return (i + 1)
n = 100000
arr = [random.randint(1, 1000000) for _ in range(n)]
start_time = time.time()
quick_sort(arr, 0, n - 1)
end_time = time.time()
print("快速排序所用时间：", end_time - start_time, "秒")
