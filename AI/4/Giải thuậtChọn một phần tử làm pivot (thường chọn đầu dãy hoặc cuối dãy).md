* **Giải thuật:**

  * Chọn một phần tử làm $pivot$ (thường chọn đầu dãy hoặc cuối dãy).
  * Chia phần còn lại của mảng làm 2 phần: $smaller$ (nhỏ hơn $pivot$) và $bigger$ (lớn hơn $pivot$). Gộp lại ta thu được mảng mới $[smaller, pivot, bigger]$.
  * Làm tương tự với $smaller$ và $bigger$ một cách [đệ quy]([https://vi.wikipedia.org/wiki/%C4%90%E1%BB%87_quy](https://vi.wikipedia.org/wiki/Đệ_quy)) sẽ cho ta kết quả là một mảng sắp xếp.

* **Minh họa:**

  <p>
      <img src='http://parallelcomp.uw.hu/files/09fig46.gif' width=500>
  </p>

  

* **Code Python:**

  ```python
  def partition(arr, low, high):
      i = (low - 1)
      pivot = arr[high]
      for j in range(low, high):
          if arr[j] < pivot:
              i = i + 1
              arr[i], arr[j] = arr[j], arr[i]
      arr[i + 1], arr[high] = arr[high], arr[i + 1]
      return (i + 1)
  
  def quickSort(arr, low, high):
      if low < high:
          pi = partition(arr, low, high)
          quickSort(arr, low, pi - 1)
          quickSort(arr, pi+1, high)
  ```

* **Độ phức tạp:**
  * Best: $\Omega (n)=nlog(n)$
  * Average: $\Theta (n) = nlog(n)$
  * Worst: $\Omicron(n) = n^2$