* **Giải thuật:**
  * Duyệt từ phần tử thứ $2$ đến cuối mảng.
  * Nếu phần tử được duyệt nhỏ hơn phần tử trước (bên trái), dịch nó dần về bên trái cho đến khi nó lớn hơn phần tử bên trái.

* **Minh họa:**

  <p>
      <img src='https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/insertion_sort.png' width=500>
  </p>

  

* **Code Python:**

  ```python
  def insertionSort(arr):
      for i in range(1, len(arr)):
          key = arr[i]
          j = i - 1
          while j >= 0 and key < arr[j]:
              arr[j + 1] = arr[j]
              j -= 1
          arr[j + 1] = key
  ```

* **Độ phức tạp:**
  * Best: $\Omega(n)=n$
  * Average: $\Theta(n)=n^2$
  * Worst: $\Omicron(n)=n^2$