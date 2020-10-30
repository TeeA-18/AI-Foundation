**1. Derivative and Gradient:**
* Đạo hàm của một điểm chính là đường tiếp tuyến tại điểm đó
* Ví dụ mình có hàm số biểu diễn doanh thu của một công ty thì khi tính đạo hàm tại một thời điểm thì mình sẽ biết công ty ấy làm ăn lơì hay lỗ tại thời điểm đó ra sao.
* Công thức áp dụng cho hàm liên tục:
    ![](https://i.imgur.com/iJlINJC.png)
* Công thức áp dụng cho hàm rời rạc:
    ![](https://i.imgur.com/ws3OzyK.png)
* Ví dụ:
     ![](https://i.imgur.com/YAXjfJq.png)
   * Ta tính đạo hàm tại điểm x hay đạo hàm trung tâm thì tính hiệu của phần tử trước và sau x rồi chia cho denta.
   * Muốn tính đạo hàm tại một điểm ta convolution với kernel sau:
   ![](https://i.imgur.com/DmzoqSR.png)
* Ý tưởng đạo hàm được áp dụng vơi kernel Sobel:
    ![](https://i.imgur.com/S8HCXMz.png)
    * Dòng ở giữa có giá trị chính nên nhân với hệ số 2
    * Kernel này được tạo ra hoàn toàn dựa vào ý tưởng của đạo hàm
    ![](https://i.imgur.com/sQlPmls.png)

* Ứng dụng đạo hàm cho edge detection
    * Kết quả khi ta correlation theo chiều X và Y
    ![](https://i.imgur.com/oaVVzLk.png)

    * Ra thông tin của các cạnh , viền 
    * Thông tin nền tảng cho đối tượng khác như ứng dụng tracking detecting dựa vào cạnh.
    * Cách thức tìm cạnh dựa vào ý tưởng đạo hàm     
    * Code: 
    ![](https://i.imgur.com/uTenx7Q.png)
    * Sobel chạy trên 1 chanel nên phải chuyển ảnh xám

**2 Interpolation:**
*  Nội suy đoán một chuyện khi có thông tin cho trước
*  Đặt vấn đề: Ví dụ ta có điểm x1 và x2 cho trược với y1 = 4 và y2 = 7. Ta sẽ dùng phép nội suy để suy ra các giá trị y của các điểm u, v, p, q.    
    ![](https://i.imgur.com/VH6IocX.png)
* Phương pháp đầu tiền Nearest neighbor:
    ![](https://i.imgur.com/z0Qt7ah.png)
    * Vì u và v gần x1 nên ta nội suy y của u và v bằng y của x1 và bằng 4
    * Vì p và q gấn x2 nên ta nội suy y của p và q bằng y của x2 bằng 7

* Phương pháp 2 nội suy theo hàm tuyến tính:
    ![](https://i.imgur.com/Kn5tHEP.png)
    * Ta sẽ viết phương trình đường thẳng đi qua hai điểm (x1,4) và (x2,7). Phương trình có dạng y = ax + b
    * Từ đó ta chiểu các điểm u , v, p, q lên đường thẳng và nội suy ra y
    * Ứng dụng khi chúng ta có 1 hình có 4 pixel mà chúng ta muốn zoom hình lên thì cần 16 giá trị pixel thì phải dùng phép nội suy đế suy ra các pixel chưa có.

* Image upsampleing:
* Đây là output của việc phóng ảnh sử dụng nearest neighbor and linear thì cho kết quả ảnh không được tốt lắm: 
        ![](https://i.imgur.com/RegPoz0.jpg)
* Code: 
    ![](https://i.imgur.com/kZ8f4Oc.png)
    * Tạo khung cho ảnh phóng to
    * Line 14-15: dùng hàm có sẵn để nội suy ảnh theo 2 phương pháp nearest neighbor và linear

**3.Vector and Matrix:**
* Vector:
    *    n là một số tự nhiên
    *    vector v có độ dài n và bao gồm các số thực: 
    ![](https://i.imgur.com/M8VJ4Ei.png)
* Matrix: 
    * Matrix có shape của hình chữ nhật
    * Có m dòng và n cột
    ![](https://i.imgur.com/jori7wZ.png)
*   Vector Operator:
     * Addition:
        * Ta cộng hai vector như sau:
        ![](https://i.imgur.com/WCmw2Ib.png) 
    *  Subtraction: 
        * Ta trừ hai vector như sau:
        ![](https://i.imgur.com/UgrFHYS.png)
    * Multiply with a number and length:
    ![](https://i.imgur.com/6Z5i7Nu.png)
* Matrix operator:
    * Ta có hai vector A và B như trong hình:
        ![](https://i.imgur.com/Gdfvdqr.png)
    * Ta có thể cộng và trừ hai ma trận dùng công thức sau:
      ![](https://i.imgur.com/wEF9aVE.png)
    * Ta có thể nhân hai ma trận như sau:
        ![](https://i.imgur.com/iMHkTXj.png)
         * Để nhân được hai ma trận thì số cột của ma trận thứ nhất phải trùng với số dọng của ma trận thứ hai
         * Sau đó ta lần lượt lấy từng phần tử ở dòng thứ nhất của ma trận A
         * Rồi nhân với từng phần tử tương ứng ở cột thứ nhất của ma trận B
         * Sau đó cộng các tích lại ta ra giá trị đầu tiên của của ma trận kêt quả
         * Phần còn lại làm tương tự
    * Ta có thể nhân một ma trận với một vecto như sau:
        ![](https://i.imgur.com/tludxeR.png)
    * Ma trận chuyển vị:
        ![](https://i.imgur.com/x5EXLxF.png)
![](https://i.imgur.com/6CvMXOB.png)
    * Việc nhân một ảnh với một ma trận không làm thay đổi giá trị ảnh mà làm thay đổi vị trí của các điểm ảnh.
    ![](https://i.imgur.com/yMHLgEt.png)
        * Ví dụ điểm p có tọa độ (3,2) t dịch chuyển pixel p theo ma trận A thì vị trí mới của điểm p là (3,-2) từ đó ta lật ngược được ảnh

* Background Subtraction:
    * Mục đích: Ta sẽ tách được phần foreground và background trong ảnh và ghép foreround vào ảnh mới.
    * Đầu tiên ta phải chụp hai ảnh có chưa mỗi background và ảnh chứa cả back and foreground:
    ![](https://i.imgur.com/v0WF1kg.png)
     * Ta coi mỗi hình là một ma trận sau đó trừ hai ma trận thì ta được hình như hình trên.
     * Sau đó ta sẽ tìm mask bằng hàm trong numpy, chỗ nào có pixel > 10 ta trả về 1 còn nhơ hơn thì trả về 0:
     ![](https://i.imgur.com/UEuc1FJ.png)
     * Từ mask những chỗ nào có giá trị bằng 1 một thì ta copy giá trị đó từ ảnh ban đầu sang background mới:
     ![](https://i.imgur.com/KwJ8jya.png)

* Dot product:
    ![](https://i.imgur.com/MhkarL9.png)
* Cosine similarity:
    * Công thức dùng để đo độ giống nhau của hai vector
    ![](https://i.imgur.com/8HeGuuf.png)

    * Ngoài ra ta còn những tính chất sau:
        ![](https://i.imgur.com/gqRHnvF.png)

**4 Stereo matching:**
* Input là ảnh trái và ảnh phải và sau đó tìm được ảnh chiều sâu
* Nhiệm vụ của mình là tìm độ lệch giữa các điểm tương ứng ở hai hình
* Hai điểm tương ứng là hai điểm có giá trị màu giống nhau
* Các điểm tương ứng sẽ nằm trên một dòng
    ![](https://i.imgur.com/ekqwKi3.jpg)


* Vs dụ điểm p trong hai hình trên sẽ có giá trị y giống nhau và nằm cùng một dòng. Nhưng giá trị x sẽ khác nhau.
* Sau đó ta sẽ tính độ lệch này và làm tương tự thế với mọi điểm ảnh
* Công thức:
    ![](https://i.imgur.com/697h6IE.png)

    * d thuộc D chính là độ lêch
    * Cái độ với mỗi giá trị d ta có 1 q thế vào cái hàm thứ hai
    * Hai màu giống nhau sẽ trả về giá trị nhỏ hơn
    * Cái q nào tương ứng với cái d đó làm cho hàm nhỏ nhât thì d chính là disparity của d.
    * Sau khi dùng thuật toán này để chạy thì ta có output:
        ![](https://i.imgur.com/BoWQTWX.png)

    * Vì giá trị một điểm ảnh bị ảnh hưởng bởi độ sáng và ảnh chụp bới hai camera và có nhiều điểm ảnh có giá trị giống nhả giống nhau nên sẽ gây ra nhiễu khi dùng disparity map
    * Trong xác suất thống kế muốn có một kết luận đúng thì dataset phải tăng lên
    * Do đó thay vì tính độ lệch của một điểm ảnh ta sẽ tính độ lệch của một window xung quanh điểm đang xét
    ![](https://i.imgur.com/J1zdy8K.png)
    * Ta sẽ có output tốt hơn: 
    ![](https://i.imgur.com/dXXBkR3.png)
    * Những điểm ảnh nào sáng thì sẽ ở gần còn điểm ảnh nào tối thì sẽ ở xa
    * Nhưng có một vấn đề xảy ra khi ta thay đổi độ sáng của điểm ảnh thì sẽ không còn đúng nữa
        * Ví dụ:
        ![](https://i.imgur.com/gfgeE6I.jpg)
        * Asumption hai điểm tương ứng có giá trị màu giống nhau đã không còn đúng khi ta thay đổi độ sáng của ảnh
        * Để giải quyết vấn đề này thì ta sẽ dùng cosine similarity
        
**5. Intergral:**
*  Công thức của tích phân:
    ![](https://i.imgur.com/2D8b6p7.png)
* Ứng dụng của tích phân:
    ![](https://i.imgur.com/UMFp6FK.png)
    
    * Ví dụ khi ta tính diện tích với độ phủ bằng 3 tương ứng với giải màu đỏ(Áp dụng cho hàm rời rạc)
    * Cách tính:
        * Đầu tiên ta tính f(3) trước tương ứng với giải màu vàng
        * Sau đó ta tình f(6) tương ứng với giải màu xanh rồi trừ đi giải màu vàng thì sẽ ra diện tích của A.