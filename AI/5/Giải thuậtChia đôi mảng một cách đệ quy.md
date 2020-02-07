* **Giải thuật:**

  * Chia đôi mảng một cách đệ quy.
  * Sắp xếp các mảng con và gộp chúng lại.

* **Minh họa:**

  <p>
      <img src='https://camo.githubusercontent.com/c9d3bf4590b7284596375ffa0cd98ee62699a757/68747470733a2f2f776562646f63732e63732e75616c62657274612e63612f253745686f6c74652f5432362f4c65637475726536466967362e676966' width=500>
  </p>

  

* **Code Python:**

  ```python
  def mergeSort(arr):
      if len(arr) > 1:
          mid = len(arr) // 2
          L = arr[:mid]
          R = arr[mid:]
          mergeSort(L)
          mergeSort(R)
          i = j = k = 0
          while i < len(L) and j < len(R):
              if L[i] < R[j]:
                  arr[k] = L[i]
                  i += 1
              else:
                  arr[k] = R[j]
                  j += 1
              k += 1
          while i < len(L):
              arr[k] = L[i]
              i += 1
              k += 1
          while j < len(R):
              arr[k] = R[j]
              j += 1
              k += 1
  ```

* **Độ phức tạp:**
  * Best: $\Omega (n)=nlog(n)$
  * Average: $\Theta (n) = nlog(n)$
  * Worst: $\Omicron(n) = nlog(n)$