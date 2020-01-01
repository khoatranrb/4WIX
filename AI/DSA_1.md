<SCRIPT SRC='https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML'></SCRIPT>
<SCRIPT>MathJax.Hub.Config({ tex2jax: { inlineMath: [['$', '$'], ['\\(', '\\)']] } })</SCRIPT>


<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">

<head>
    <title>Sắp xếp nổi bọt</title>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}});
      </script>
    <script type="text/javascript"
        src="http://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
        </script>
    <style type="text/css">
        .ngu {
            margin-right: 10px;
        }
    </style>
    <style>
        div {
            margin-bottom: 15px;
            padding: 4px 12px;
        }

        .note {
            background-color: #ddffdd;
            border-left: 6px solid #4CAF50;
        }
    </style>
</head>

<body>
    <h2>Góc nhìn: </h2>
    <div class="ngu">
        <li>Dưới góc nhìn của <b>Sắp xếp nổi bọt</b> , mảng đã sắp xếp là mảng mà trong hai phẩn tử bất kì liền kề,
            <i>phần tử đứng sau luôn lớn hơn phần tử đứng trước.</i> </li>
    </div>

    <h2>Thuật toán: </h2>
    <div class="ngu">
        <li><b>B1: </b>Duyệt mảng từ đầu đến cuối, nếu <i>phần tử đứng sau nhỏ hơn phần tử đứng trước</i> thì đổi chỗ
            chúng.</li>
        <li><b>B2: </b>Nếu duyệt hết một vòng mà không phải đổi chỗ bất kỳ phần tử nào ==> mảng đã sắp xếp, dừng thuật
            toán. Nếu không, lặp lại <b>B1</b>.</li>
    </div>

    <h2>Code Python: </h2>
    <!-- HTML generated using hilite.me -->
    <div
        style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;">
        <pre style="margin: 0; line-height: 125%"><span style="color: #008800; font-weight: bold">def</span> <span style="color: #0066BB; font-weight: bold">bubbleSort</span>(arr):
        n <span style="color: #333333">=</span> <span style="color: #007020">len</span>(arr)
        <span style="color: #008800; font-weight: bold">for</span> i <span style="color: #000000; font-weight: bold">in</span> <span style="color: #007020">range</span>(n):
            swap <span style="color: #333333">=</span> <span style="color: #007020">False</span>
            <span style="color: #008800; font-weight: bold">for</span> j <span style="color: #000000; font-weight: bold">in</span> <span style="color: #007020">range</span>(n<span style="color: #333333">-</span><span style="color: #0000DD; font-weight: bold">1</span>):
                <span style="color: #008800; font-weight: bold">if</span> arr[j]<span style="color: #333333">&gt;</span>arr[j<span style="color: #333333">+</span><span style="color: #0000DD; font-weight: bold">1</span>]:
                    arr[j], arr[j<span style="color: #333333">+</span><span style="color: #0000DD; font-weight: bold">1</span>] <span style="color: #333333">=</span> arr[j<span style="color: #333333">+</span><span style="color: #0000DD; font-weight: bold">1</span>], arr[j]
                    swap <span style="color: #333333">=</span> <span style="color: #007020">True</span>
            <span style="color: #008800; font-weight: bold">if</span> swap <span style="color: #333333">==</span> <span style="color: #007020">False</span>:
                <span style="color: #008800; font-weight: bold">return</span> <span style="color: #007020">None</span>
    </pre>
    </div>

    <h2>Độ phức tạp thuật toán: </h2>
    <div class='ngu'>
        <li>Tốt nhất:
            <?xml version="1.0" encoding="utf-8" standalone="no"?>
            <math xmlns="http://www.w3.org/1998/Math/MathML" title="O(n)=n ">
                <mrow>
                    <mi>O</mi>
                    <mo maxsize="1">(</mo>
                    <mi>n</mi>
                    <mo maxsize="1">)</mo>
                    <mo>=</mo>
                    <mi>n</mi>
                </mrow>
            </math></li>

        <li>Trung bình:
            <?xml version="1.0" encoding="utf-8" standalone="no"?>
            <math xmlns="http://www.w3.org/1998/Math/MathML" title="O(n)=n^2 ">
                <mrow>
                    <mi>O</mi>
                    <mo maxsize="1">(</mo>
                    <mi>n</mi>
                    <mo maxsize="1">)</mo>
                    <mo>=</mo>
                    <msup>
                        <mrow>
                            <mi>n</mi>
                        </mrow>
                        <mrow>
                            <mn>2</mn>
                        </mrow>
                    </msup>
                </mrow>
            </math></li>
        <li>Xấu nhất:
            <?xml version="1.0" encoding="utf-8" standalone="no"?>
            <math xmlns="http://www.w3.org/1998/Math/MathML" title="O(n)=n^2 ">
                <mrow>
                    <mi>O</mi>
                    <mo maxsize="1">(</mo>
                    <mi>n</mi>
                    <mo maxsize="1">)</mo>
                    <mo>=</mo>
                    <msup>
                        <mrow>
                            <mi>n</mi>
                        </mrow>
                        <mrow>
                            <mn>2</mn>
                        </mrow>
                    </msup>
                </mrow>
            </math></li>
    </div>
    <p><i>Hà Nội ngày 31/12/2019.</i></p>
    <p><strong>Tran Van Khoa</strong></p>
</body>
