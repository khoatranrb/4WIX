#### 1. Phân phối Bernoulli

* Phân phối **Bernoulli** mô phỏng kết quả khi tung một con xúc xắc với xác suất có mặt *head* ($x=1$, *"thành công"*) là $p$ và xác suất xảy ra mặt *tail* ($x=0$, *"thất bại"*) là $q=1-p$.

  * $x\in S_x=${$0,1$}, $0\leq p\leq 1$

  * $p(x)=p^x(1-p)^{1-x}$

    <p>
        <img src='https://raw.githubusercontent.com/khoatranrb/4WIX/master/Stat/f_ber.png' width=400
    </p>

  * Đồ thị hàm tích lũy xác suất:

    <p>
        <img src='https://raw.githubusercontent.com/khoatranrb/4WIX/master/Stat/F_ber.png' width=400
    </p>

  * $E[x]=p$, $VAR[x]=p(1-p)$

#### 2. Phân phối nhị thức (Binomial)

* Mô phỏng xác suất *"thành công"* $x$ lần trong $n$ lần thực hiện phép thử **Bernoulli**.

  * $x\in S_x=${$0,1,2,...,n$},  $0\leq p\leq 1$

  * $\begin{align*}p(x)=\begin{pmatrix}n\\x \end{pmatrix}p^x(1-p)^{n-x}\end{align*}$

    <p>
        <img src='https://raw.githubusercontent.com/khoatranrb/4WIX/master/Stat/bin.png' width=600
    </p>

  * $E[x]=np$, $VAR[x]=np(1-p)$

#### 3. Phân phối hình học (Geometric)

* *Phiên bản 1:* Mô phỏng xác suất *"thất bại"* $x$ lần trước khi *"thành công"* của phép thử **Bernoulli**.

  * $x\in S_x=${$0,1,2,...$},  $0\leq p\leq 1$

  * $p(x)=p(1-p)^x$

  * $E[x]=\frac{1-p}{p}$, $VAR[x]=\frac{1-p}{p^2}$

* *Phiên bản 2:*  Mô phỏng xác suất cần $x$ lần thực hiện phép thử **Bernoulli** để có lần đầu tiên *"thành công"*.

  * $x\in S_x=${$1,2,...$},  $0\leq p\leq 1$

  * $p(x)=p(1-p)^{x-1}$

  * $E[x]=\frac{1}{p}$, $VAR[x]=\frac{1-p}{p^2}$

#### 4. Phân phối nhị thức âm (Negative Binomial)

* Mô phỏng xác suất *cần* $x$ lần thực hiện phép thử **Bernoulli** để có $r$ lần *"thành công"*.

  * $x\in S_x=${$r,r+1,r+2,...$}, $r\in N$, $0\leq p\leq 1$

  * $\begin{align*}p(x)=\begin{pmatrix}x-1\\r-1 \end{pmatrix}p^r(1-p)^{x-r}\end{align*}$

  * $E[x]=\frac{r}{p}$, $VAR[x]=\frac{r(1-p)}{p^2}$

#### 5. Phân phối đều (Uniform)

* **Phân phối đều** xảy ra nếu xác suất xảy ra các trường hợp là như nhau.

  * $x\in S_x=${$1,2,...,L$}, $L\in N$

  * $p(x)=\frac{1}{L}$

    <p>
        <img src='https://raw.githubusercontent.com/khoatranrb/4WIX/master/Stat/f_uni.png' width=300
    </p>

  * Đồ thị hàm tích lũy xác suất:

    <p>
        <img src='https://raw.githubusercontent.com/khoatranrb/4WIX/master/Stat/F_uni.png' width=300
    </p>

  * $E[x]=\frac{L+1}{2}$, $VAR[x]=\frac{L^2-1}{12}$

#### 6. Phân phối Poisson

* Mô phỏng xác suất số lần xảy ra biến cố trong một đơn vị thời gian, biết trong một đơn vị thời gian biến cố xảy ra trung bình $\alpha$ lần.

  * $x\in S_x=${$0,1,2,...$}

  * $p(x)=\frac{\alpha^x}{x!}e^{-x}$

    <p>
        <img src='https://www.statisticshowto.datasciencecentral.com/wp-content/uploads/2013/10/poisson-distribution.png'width=500>
    </p>

  * $E[x]=\alpha, VAR[x]=\alpha$

#### 7. Phân phối Zipf

* Giả sử các từ ngữ được xếp hạng theo độ thông dụng. Gọi $S_x=${$1,2,...,L$} là thứ tự của các từ đó, với $L$ là số lượng từ có trong danh sách.

  * $x\in$ $S_x=${$1,2,...,L$}

  * $p(x)=\frac{1}{c_L}\frac{1}{x}$ với $c_L=\sum_{j=1}^L\frac{1}{j}$

    <p>
        <img src='https://miro.medium.com/max/589/1*Ge5uKAcGumIz1Qw3TXhq6g.png'width=500>
    </p>

  * $E[x]=\frac{L}{c_L}, VAR[x]=\frac{L(L+1)}{2c_L}-\frac{L^2}{c_L^2}$

#### Tham khảo

* [1] <a href='https://dominhhai.github.io/vi/2017/10/prob-com-var/' target='_blank'>Một số phân phối phổ biến</a>.

