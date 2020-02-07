* **Giải thuật:**

  * Với **selection sort**, mảng được sắp xếp là mảng mà mỗi phần tử đều nhỏ hơn tất cả các phần tử bên phải nó.
  * Vậy thuật toán của nó là:
    * Duyệt mảng lần lượt từ trái qua phải
    * So sánh phần tử $I$ được duyệt với tất cả các phần tử bên phải nó:
      * Nếu $I$ nhỏ nhất, $pass$. Nếu không, đổi chỗ $I$ và phần tử nhỏ nhất đó.

* **Minh họa:**

  <p>
      <img src='https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/selection_sort.png' width=400>
  </p>

  

* **Code Python:**

  ```python
  def selectionSort(arr):
      l = len(arr)
      for i in range(l):
          p = i
          for j in range(i,l):
              if arr[j]<arr[p]:
                  p = j
          arr[i], arr[p] = arr[p], arr[i]
  ```

* **Độ phức tạp:**

  * Best: $\Omega (n)=n^2$
  * Average: $\Theta (n) = n^2$
  * Worst: $\Omicron(n) = n^2$

