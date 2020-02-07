* Biến đổi cường độ sáng là một trong những kỹ thuật xử lý ảnh đơn giản nhất. Bài viết này giới thiệu đến bạn đọc một số phương pháp phổ biến.
* Chúng ta quy ước giá trị *pixel* trước và sau khi xử lý lần lượt là $r$ và $s$, cùng với đó là hàm chuyển đổi $T$ ánh xạ $r$ sang $s$.
* Vì chúng ta chỉ làm việc với ảnh kỹ thuật số nên các giá trị $r$ và $s$ là các giá trị nguyên thuộc khoảng $[0,255]$.

### 1. Image negatives

* $s=T(r)=255-r$

  <p>
      <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/img_neg.png" width=400>
  </p>

  

* Thường được dùng để làm rõ các chi tiết trắng, xám trên ảnh có vùng tối là chủ đạo. Ảnh output được gọi là *ảnh âm bản*.

  <p>
       <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/neg.png" width=800>
  </p>

* Thực tế là nội dung hai ảnh trên là tương đồng nhau. Tuy nhiên một số người có thể xem xét ảnh dễ dàng hơn trên *ảnh âm bản*.

### 2. Log transformation

* $s=T(r)=clog(1+r)$

  * Với $c$ là hằng số. $r$ bị giới hạn trong khoảng $[0,255]$, ta có thể chọn $c$ để giới hạn output $s$.
  * Với $c=\frac{255}{log(256)}$, $s\in [0,255]$.

  <p>
       <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/img_log.png" width=400>
  </p>

* **Nhận xét:** 

  * $s>r$ với $\forall r$. **Log transformation** dùng làm sáng các ảnh có độ sáng thấp.
  * Với $r$ thấp, đồ thị dốc và thoải hơn khi $r$ lớn. **Log transformation** ánh xạ vùng *pixel* nhỏ (tối), hẹp thành vùng rộng hơn, lớn (sáng) hơn và ngược lại, vùng *pixel* lớn được nén lại.

  <p>
         <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/log.png" width=1000>
  </p>

### 3. Power-law (Gamma) transformation

* $s=T(r)=cr^{\gamma}$

  * $c$ là hằng số để giới hạn output $s$
  * Với $c=\frac{1}{255^{\gamma}}$, $s\in [0,255]$.

  <p>
         <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/gamma.png" width=500>
  </p>

  

* **Nhận xét:** 

  * Ta dùng $\gamma>1$ sẽ thu được ảnh *tối hơn* ảnh gốc và ngược lại với $\gamma<1$.

  <p>
             <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/gamma1.png" width=1000>
  </p>

  <p>
       <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/gamma2.png" width=1000>
  </p>

  

  

  * **Gamma transformation** cũng có các nhận xét giống với **Log transformation** ở trên.
  * Để có được ảnh output có chất lượng như mong muốn, $\gamma$ sẽ được thử với nhiều giá trị khác nhau. Vì vậy **Gamma transformation** thường được dùng để điều chỉnh độ tương phản (*contrast manipulation*).

### 4. Piecewise linear transformation

#### 4.1. Contras stretching

<p>
    <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/constrast.png" width=500>
</p>

* **Contrast stretching** dùng để tăng độ tương phản cho ảnh có độ tương phản thấp (là ảnh có [biểu đồ *histogram*](https://en.wikipedia.org/wiki/Image_histogram) quá tập trung vào một vùng).

<p>
    <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/his_contrast.png" width=500>

* **Nhận xét:**
  * Đồ thị chia làm 3 vùng rõ rệt:  $r<r1$, $r1<r<r2$ và $r>r2$.
  * Việc chọn $(r1,s1), (r2,s2)$ phụ thuộc vào *histogram* của ảnh muốn xử lý và kết quả mong muốn của ảnh output. Ta muốn kéo dãn vùng *pixel* có mật độ cao thì cần chọn $(r1,s1), (r2,s2)$ sao cho đồ thị $T(r)$ trong vùng *pixel* có mật độ cao đó phải ***dốc*** hơn các vùng khác.

* **Ví dụ:**

  * Ảnh gốc:

    <p>
        <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/cs.jpg" width=300>
    </p>

    

  * **Contrast stretching** với $(r1,s1)=(80,20)$, $(r2,s2)=(160,240)$:

    <p>
        <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/res_cs.jpg" width=300>
    </p>

  * Biểu đồ *histogram*:

    <p>
        <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/Figure_1.png" width=600>
    </p>

    

#### 4.2 Intensity-level slicing

* **Mục đích:**

  * Làm nổi bật lên một vùng *pixel* nhất định.

    <p>
        <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/itensity_level.png" width=800>
    </p>

  * Trên đây là hai trường hợp được xử dụng phổ biến hơn cả:

    * Trường hợp **A** cho kết quả là một ảnh nhị phân:

      <p>
          <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/i_levelA.png" width=600>
      </p>

    * Trường hợp **B** làm *highlight* một khoảng *pixel* nhất định, phần còn lại không đổi:

      <p>
          <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/i_level.png" width=600>
      </p>

#### 4.3. Bit-plane slicing

* Giá trị *pixel* là một số nguyên được tạo thành từ một dãy nhị phân 8 bits. Ý tưởng của **bit-plane slicing** là: thay vì biểu diễn ảnh bằng giá trị của các *pixel*, ta biểu diễn nó bằng 8 tầng ảnh, mỗi tầng tương ứng với mỗi bit.

  <p><img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/bit_plane.png" width=600>

  
* **Ví dụ:**
  * Một *pixel* $I$ có giá trị $169$, giá trị nhị phân của nó là $[10101001]$. Khi phân tích thành 8 ảnh **bit-plane slicing**, giá trị của nó lần lượt là:
    * Bit 0: $[00000001]$, $1$
    * Bit 0: $[00000000]$, $0$
    * Bit 0: $[00000000]$, $0$
    * Bit 0: $[00001000]$, $8$
    * Bit 0: $[00000000]$, $0$
    * Bit 0: $[00100000]$, $32$
    * Bit 0: $[00000000]$, $0$
    * Bit 0: $[10000000]$, $128$
    
  * Việc phân rã ảnh gốc thành các thành phần như vậy có ích cho việc phân tích mối quan hệ và tầm quan trọng của các bit thành phần cấu tạo nên ảnh.
  
    <p>
        <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/9money.png" width=1200>
        <center><caption>Ảnh gốc và 8 bit-plane</caption></center>
    </p>
  
    
  
  * Trong kỹ thuật nén ảnh, **bit-plane slicing** sẽ chọn vài *"plane"* tốt để tái cấu trúc ảnh.
  
    <p>
        <img src="https://raw.githubusercontent.com/khoatranrb/4WIX/master/AI/Img/cons_money.png" width=1200>
        <center><caption>Lần lượt theo thứ tự: bit(8), bit(8,7), bit(8,7,6), ảnh gốc</caption></center>
    </p>

### Tham khảo:

[1] [Intensity Transformation|The AILearner](https://theailearner.com/2019/01/01/intensity-transformation/)

[2] [Digital Image Processing](https://drive.google.com/open?id=1IR4W0b_6swooZX_0VnfXylJYmZJc3UEZ)

* [Souce code](https://github.com/khoatranrb/4WIX/blob/master/AI/Untitled.ipynb)