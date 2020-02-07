##### Tọa độ

* Cho $B=${$v_1,v_2,...,v_n$} là cơ sở của không gian vector $V$  và $x\in V$, ta có:
  $$
  x = c_1v_1+c_2v_2+...+c_nv_n
  $$

* $c_1,c_2,...,c_n$ được gọi là **tọa độ của x trong cơ sở B**, ký hiệu:
  $$
      \begin{align*}
          [x]_B=\begin{bmatrix}
              c_1 \\
              c_2 \\
              : \\
              c_n \\
          \end{bmatrix}
      \end{align*}
  $$

* *Ví dụ 1:*

  * Cho $x=(1,-3,2)$ và $B=${$(1,0,0),(0,0,1),(0,1,0)$}, ta có:
    $$
    \begin{align}
            x &= (1,-3,2)\\ 
            &=1\times(1,0,0)+ 2\times(0,0,1)-3\times(0,1,0)
        \end{align}
    $$

    $$
    \rightarrow [x]_B= \begin{align*}
            \begin{bmatrix}
                1 \\2\\-3
            \end{bmatrix}
        \end{align*}
    $$

  * *Ví dụ 2:* Vẫn là $x=(1,-3,2)$ như ví dụ trên và $B'=${$(1,1,0),(2,0,1),(0,-1,0)$}:

    * *Cách 1:*
      $$
      \begin{align}        x &= (1,-3,2)\\         &=-3\times(1,1,0)+ 2\times(2,0,1)+0\times(0,-1,0)    \end{align}
      $$

      $$
      \rightarrow [x]_{B'}= \begin{align*}
              \begin{bmatrix}
                  -3 \\2\\0
              \end{bmatrix}
          \end{align*}
      $$

    * *Cách 2:* Giải phương trình $B'[x]_{B'}=[x]_{R^n}$, cụ thể:
      $$
      \begin{align*}
              \begin{bmatrix}
                  1&2&0\\
                  1&0&-1\\
                  0&1&0\\
              \end{bmatrix}
              \begin{bmatrix}
                  c_1\\
                  c_2\\
                  c_3\\
              \end{bmatrix}
              =\begin{bmatrix}
                  1\\
                  -3\\
                  2\\
              \end{bmatrix}
          \end{align*}
      $$

      * Giải phương trình trên ta có nghiệm $c_1=-3$,$c_2=2$,$c_3=0$.

* Qua 2 ví dụ trên, ta thấy **tọa độ một vector trong các cơ sở khác nhau là khác nhau**.

##### Ma trận chuyển cơ sở

* **Định nghĩa:** Với $P[x]_{B'}=[x]_B$, ta nói $P$  **là ma trận chuyển có sở từ B' sang B**. Ngược lại, $P^{-1}$  **là ma trận chuyển có sở từ B sang B'**.

* **Bổ đề:** Cho $B=${$v_1,v_2,...,v_n$} và $B'=${$u_1,u_2,...,u_n$} là hai cơ sở trong không gian vector $V$. Nếu:
  $$
  v_1 = c_{11}u_1+c_{21}u_2+...+c_{n1}u_n \\
  v_2 = c_{12}u_1+c_{22}u_2+...+c_{n2}u_n  \\
  : \\
  v_n = c_{1n}u_1+c_{2n}u_2+...+c_{nn}u_n 
  $$
  thì *ma trận chuyển cơ sở từ  $B$  sang* $B'$  là:
  $$
  \begin{align*}
          P^{-1}=Q=\begin{bmatrix}
              c_{11}& c_{12}&...& c_{1n}\\
              c_{21}& c_{22}&...& c_{1n}\\
              c_{n1}& c_{n2}&...& c_{nn}\
          \end{bmatrix}
      \end{align*}
  $$

* **Định lý:** Lấy ví dụ từ **bổ đề** trên, ta có thể tìm $P^{-1}$ bằng cách:
  $$
  [B'|B]\rightarrow[I_n|P^{-1}]
  $$
  với $[B^{-1}|B] = [u_1\ u_2\ ...\ u_n| v_1\ v_2\ ...\ v_n ]$.

* *Ví dụ:* Lấy $B$  và $B'$ từ ví dụ ở trên:
  $$
  \begin{align*}
          B=\begin{bmatrix}
              1&0&0\\
              0&0&1\\
              0&1&0\\
          \end{bmatrix} và \
          B'= \begin{bmatrix}
              1&2&0\\
              1&0&-1\\
              0&1&0\\
          \end{bmatrix}
      \end{align*}
  $$
  ta có:
  $$
  \begin{align*}
          [B'|B]=\begin{bmatrix}
              1&2&0&1&0&0\\
              1&0&-1&0&0&1\\
              0&1&0&0&1&0\\
          \end{bmatrix}
      \end{align*}
  $$
  biến đổi *Gauss* ta đươc:
  $$
  \begin{align*}
          [I_3|P^{-1}]=\begin{bmatrix}
              1&0&0&1&-2&0\\
              0&1&0&0&1&0\\
              0&0&1&1&-2&-1\\
          \end{bmatrix}
      \end{align*}
  $$
  
  $$
  \begin{align*}
          \rightarrow P^{-1}=\begin{bmatrix}
              1&-2&0\\
              0&1&0\\
              1&-2&-1\\
          \end{bmatrix}
      \end{align*}
  $$
  

