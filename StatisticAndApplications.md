# Statistics and Applications:
 
 **1.Mean:**
     We find the mean by adding up all the components and then deviding by the number of components:  
    <img src="https://i.imgur.com/8TCjZTh.png" alt="drawing" style="width:200px;"/>
    
    Example: Given the data: X = {2,8,6,9,7,4}
                         N = 6
            ==> Mean of X = 1/6 *(2+8+6+9+7+4) = 6  

- The "mean" of a sample is the summary statistic computed with the previous formula.
    
    Example code:
        ![](https://i.imgur.com/dOLh1El.png)

    -- This function use to calculate the mean:
      
   - Declare the function name 'calculate_mean' with the parameter 'numbers'
   - Use function **sum** in python to calculate the sum of arguments pass to the function
   - Use function **len** in python to calculate the length of arguments pass to the function
   - Calculate the **mean** follow the formula 
   - Return the value of **mean** of the arguments pass tho the function.


**2.Application of Mean:**

-    Blurrung the photos:
    -    Make the data loss of detail
-    We take every section of data in picture then calculate the mean. Finally assign it back to the picture
-    Correlation:        
           ![](https://i.imgur.com/JyHsA5M.png)
    +) Example we have the picture include 9 pixels(v1,v2,..v9), with the kernel (2x2) with 4 weight:
        1.  Để tính correlation chúng ta cho kernel trượt trên các ma trận pixel 2x2.
        2. Khi kernel trượt trên ma trận 2x2 đầu tiên gồm 4 pixel v1,v2,v3,v4 thì ta sẽ có m1:
            ***m1 = v1w1 + v2w2+ v3w3 + v4w4.***
        3. Tương tự như vậy chúng ta tính được m2,m3,m4
        ![](https://i.imgur.com/oXx7Qam.png)
        4. Sau khi  image(3x3) correlation(*) với kernel (2x2) chúng ta có output(2x2) với 4 pixel m1,m2,m3,m4
        5. Mục đích chúng ta tìm hiểu về correlation bới vì: 
        Tính mean chính là phép correlation với kernel có các trọng số là 1 sau đó chia cho số lượng trọng số. 
        **Example: calculate mean of [v1,v2,v3,v4]**:
            - Mean = 1/4 * (v1w1 + v2w2+ v3w3 + v4w4)
        6. Chúng ta có thể nói **correlation** là phép tổng quát. Đối với trường hợp trọng số của kernel bằng 1 --> ***Phép tính mean***
    +) Ví dụ hình với hình xám (có 1 chanel-mặt phẳng)
    ![](https://i.imgur.com/iX5Dn7p.png)
    1 Khi correlation với kernel (5x5) thì sẽ được output có size là 28x28.
    +) Ví dụ với hình màu có (có 3 chanel-mặt phẳng):
    ![](https://i.imgur.com/b3Boczo.png)
    1 Nếu muốn correlation hình có 3 chanel thì ta sẽ lấy từng mặt phẳng hay chanel ta correlation với kernel như ví dụ 1 thì sẽ ra từng mặt phẳng tương ứng.
     
Khi chúng ta muốn correlation một image có nhiều chanel thì ta lấy tưng mặt phẳng hay chanle ta correlation với kernel rồi ghép các mặt phẳng tương ứng lại. 


+) Khi mà correlation thì hình của chúng ta sẽ mất các biên thì sẽ có một số cách để giữ lại biên của hình: 
    - Chèn thêm giá trị 0 vào các biên

**3. Correlation function:**
*  Mục đích của ngôn ngữ Python là dùng các hàm có sẵn được code bới ngôn ngư C và C++ dùng để giảm thiểu thời gian hoàn thành công việc. 
* Nên việc dùng hàm for là tối kị trong Python vì nó sẽ làm thời gian tính toán rất chậm
* Một sô hàm hỗ trợ để tính correlation: 

![](https://i.imgur.com/aMRss17.png)

* Kernel chính là ma trận hai chiều. 
* Nếu muốn tình Mean thì nhân với kernal có giá trị bằng 1 và chia cho số lượng trọng số 
* Ví dụ kernel để tính **mean**:
![](https://i.imgur.com/lDG47tQ.png)

* Giải thích hàm để tính mean: 
![](https://i.imgur.com/NUsJmus.png)

* Ví dụ 1: Đưa ảnh lên và làm mờ ảnh:
![](https://i.imgur.com/WGikJkf.png)
    -->Output sau khi shift enter:
    ![](https://i.imgur.com/cu6JGrI.png)
  
  * Khi chúng ta correlation bằng một kernel có số trọng số lơn hơn thì ảnh sẽ mờ hơn, bời vì:
    * Khi chúng ta trượt kernel lớn hơn trên hình thì kernel sẽ bao trùm một giải dữ liệu lớn hơn.
    * Sau đó nó sẽ tính mean để lấy giá trị đại diện --> dữ liệu sẽ mất tính chi tiết và hình sẽ mờ hơn.

* Ví dụ 2: Đưa ảnh lên và làm mờ khuôn mặt với vị trí biết trước:
![](https://i.imgur.com/EeMWd6f.png)
    * Trong ví dụ này ta cắt một phần của ảnh ra rồi gán vào một biến khác (trong ví dụ trên là **'roi'**)
    * Sau đó ta sử dụng các hàm sẵn có để xử lý biến này
    * Sau đó gán ngược lại giá trị của biến bằng phần ảnh mình đã lấy ra
    * Result: 
    ![](https://i.imgur.com/vqOQJo0.png)
    * Ví dụ đầu tiên thì chúng ta làm mờ cả hình
    * Còn trong ví dụ này thì chúng ta cắt phần mặt ra và làm mờ sau đó copy ngược vào hình nên có thể thấy chỉ có phần khuôn mặt bị làm mờ
    * Lưu ý hình này có kiểu numpy nên lấy ra các giá trị rất đơn giản.
* Ví dụ 3 Làm mờ khuôn mặt dựa vào hàm xác định khuôn mặt dựa vào file training có sẵn:
    ![](https://i.imgur.com/6qSMz5A.png)
    * Trong ví dụ này chúng ta sử dụng sẵn hàm xác định khuôn mặt dựa vào file training có sẵn
    * Sau đó tải ảnh lên và đưa về dạng ảnh xám
    * Dung list **'faces'** để chứa các giá trị khuôn mặt được xác định trong hình
    * Sau đó vẽ hình chữ nhật xung quanh khuôn mặt dựa vào 3 giá trị (x,y) - điểm trái trên , w-chiều rộng, h-chiều cao.
    * Gọi lặp lại 3 lần hàm cv2.filter2D để làm mờ ảnh
    
**4. Stereo Matching**:
* Trong Computer Vision có một lĩnh vức là stereo matching:
    * Sẽ có hai camera một bên trái và một bên phải để giả lập mắt của con người để xác định chiều sâu của vật thông qua ảnh
    * Ví dụ giữa ảnh trái và ảnh phải:
    ![](https://i.imgur.com/9dz2kol.png)
    * Mỗi điểm ở ảnh này thì sẽ có một điểm tương ứng ở ảnh kia 
    * Hai điểm tương ứng sẽ có độ lệch nhau từ đó suy ra được chiều sâu của ảnh đến camera
    * Nhưng với khả năng phát triển của deeplearning khi học được rất nhiều kinh nghiệm từ ảnh thì ta chỉ cần 1 hình để xác định chiều sâu của ảnh


**5. Median:**
*    Tại sao phải tính median:
       *    Chúng ta có thể thấy mean đại diện tốt cho dự liệu có tính đột biến thấp đến trung bình
        *    Nhưng với tập dữ liệu có tính đột biến cao như hình nhiễu thì sẽ đại diện không tốt
        *    Chúng ta tính median bằng cách lấy giá trị ở giữa của một tập đã sắp xếp tăng dần hoặc giảm dần.
        ![](https://i.imgur.com/zFYJCqQ.png)
        *    Example 1: X = [4,8,2,10,9]
                      N = 5
                ==> Step 1: sort X --> S = [2,4,8,9,10]
                    Step 2: N = 5 --> m = S4 = 8
        *    Example 2: X = [2,9,5,7,8,4]
                      N = 6
                ==> Step 1: sort X --> S = [2,4,5,7,8,9]
                    Step 2: n =6 --> m = (S3 + S4)/2 = 6
        * Example code để tính median: 
        ![](https://i.imgur.com/tnp98gL.png)
        * #1 Khởi tạo hàm tính median với tham số truyền vào hàm là một list(numbers)
        * #2 Tính số lượng phần tử của list sử dụng hàm len()
        * #3 Sử dụng hàm sort() để sắp xếp dãy
        * #4 Xét xem N có chia hêt cho 2 hay không, tùy N chẵn hay lẻ sẽ có cách tìm median riêng
        * #6 Trả về giá trị của median
* Median có tác dụng dùng để khử nhiễu. 
* Nhưng khi tăng kernel thì ta có thể khử nhiễu tốt hơn nhưng hình sẽ bị mờ hơn
* Ví dụ khử nhiễu bằng kernel(9x9)
![](https://i.imgur.com/msMFy2G.png)
* Code để demo:
    ![](https://i.imgur.com/48Fe6NF.png)
    * Trong ví dụ này chúng ta dùng hàm medianBlur() trong OpenCV để tính median với hai tham số truyền vào là:
        * image
        * kernel

**6.Histogram:**
* Hình mình biết trược giá trị pixel(0-255)
* Chia thành 256 bin mỗi bin chứa số lượng pixel có cùng giá trị.
![](https://i.imgur.com/mX6JVqE.png) 
    * Hình tối giá trị phân bố sang bến trái
    * Hình có độ sáng trung bình dữ liệu phấn bố đều
    * Hình có độ sáng cao dữ liệu tập trung bên phải
 
 * Ứng dụng của histogram giúp để cân bằng ánh sáng của điểm
    
**7. Variance:**
* Variance mô tả độ phân tán dữ liệu quanh giá trị trung bình. 
* Ví dụ hai biến có chung giá trị trung bình nhưng có giá trị varience khác nhau hay độ đột biến khác nhau.
 ![](https://i.imgur.com/lHfsB3V.png)
 
 * Example: 

 * Code: 
    ![](https://i.imgur.com/MMHJ0zb.png)
 * Ứng dụng của variance(standard-deviation) là tìm texture của ảnh
     * Ví dụ khi ta đưa dòng dữ liệu của một ảnh lên và tính giá trị standard-deviation:
     ![](https://i.imgur.com/9McQjut.png)
     * Trong hình đầu tiên những phần có giá trị chạy ngang thì có dữ liệu phân tán cục bộ thấp nên khi tính mean cũng sẽ gần bằng giá trị của những phần có giá trị dữ liệu chạy ngang
     * Nên giá trị variance sẽ thấp
     * Hình bên là biểu đồ biểu diễn giá trị variance của hình thứ nhất
* Ý tưởng về việc tìm textture thông qua varience hay standard deviation:
    * Đầu tiên chúng ta sẽ chuyển ảnh lên và đưa về dạng ảnh xám(có 1 kênh) để dễ tính toán
    ![](https://i.imgur.com/NcTl22Z.png)
    * Sau đó lấy từng window(5x5 với 25 pixel) rồi áp từng điểm vào ta có hình sau: 
    ![](https://i.imgur.com/S3x4rNh.png)
    * Sau đó cắt những cạnh có giá trị [0,10] vì nó sẽ mờ và không có nhiều tác dụng
    * Sau đó scale giá trị pixel của các cạnh lên để cho hình texture rõ hơn
    * Ví dụ khí ta biểu diễn ảnh bằng matplotlib
    ![](https://i.imgur.com/GfI0hgV.png)
    * Những vùng nào có giá trị bằng nhau như hình ở trên thì sẽ có variance thấp 
    * Những hình nào có giá trị mấp mô thì variance sẽ cao
* Example code:
     ![](https://i.imgur.com/wf1EjNc.png)
    * line code 1 - 4: Import các thư viện cần thiết để gọi hàm
    * Line 5-7: Load hình lên và đưa về ảnh xám với 1 chanel
                Sau đó lưu hình vào một file
    * Line 10: đưa các giá trị pixel về kiểu float
    * Line 11-13: dùng hàm có sẵn để tính standard deviation với kernel 7x7 và lưu ảnh vào file
    * Line 14: Loại bỏ các giá trị pixel < 20
    * Line 17-21: Tìm giá trị max của pixel và scale giá trị ảnh lên cho rõ nhìn.

**8 Correlation coeffition:**   
* Công thức này để tính độ tương quan giữa hai biến
* Ví dụ chúng ta có hai biến là số tiền thuê người nổi tiếng để quảng cáo và doanh thu của công ti
* Dùng công thức này ta có thể tính được rằng khí thuê người này để quảng cáo thì doanh thu công ti có tăng hay không
* Công thức:
![](https://i.imgur.com/2UI9lb1.png)
* Nếu hệ số tương quan = 1 thì hai biến tỉ lệ thuận
* Nếu hệ số tương quan = -1 thì hai biến tỉ lệ nghịch
* Ta có thêm những tính chất sau: 
    ![](https://i.imgur.com/m4nwLYx.png)
    * Nếu u = ax + b và v = cy + d thì hệ số tương quan của x và y bằng hệ số tương quan của u và v
    ![](https://i.imgur.com/87yb6tU.png)
    * Chứng minh: 
    ![](https://i.imgur.com/cCG2EmA.png)
    * Ta lần lượt thay a = ax, b = by vào công thức đầu.
    * Sau đó ta đưa các phần từ chung của cả tử lẫn mẫu ra ngoài
    * Trong trường hợp này là a và b sau đố rút gọn trên cả tử và mẫu nên ta sẽ ra công thức ban đầu.
    ![](https://i.imgur.com/N3ukQFn.png)
    * Trong hình trên ta áp dụng tính chất mean(x+c) = mean(x) + c nên ta có thể triệt tiêu được c và d ở trên tử số
    * Ở dưới mẫu số ta áp dụng tính chất  var(x+c) = var(x) bởi vì c là hằng số  nên ta cũng triệt tiêu được c và d ở dưới mẫu
* Ứng dụng:
    * Ứng dụng cho patch matching:
    ![](https://i.imgur.com/Hope33T.png)
        * Ví dụ ta có 4 bức ảnh và ta sẽ tìm độ tương quan và giống nhau của 4 ảnh đó.
        * Vì khi ta đưa lên để xử lí thì ta sẽ đưa ảnh về dạng ảnh xám nên những viền ngoài nó sẽ cho là giống nhau 
    * Công thức này vẫn hoạt động tốt dù có thay đổi độ sáng của hình: 
    ![](https://i.imgur.com/caJeHEl.png)
    * Code:
    ![](https://i.imgur.com/VBHdG17.png)
        * Đầu tiên ta import các thư viện để gọi các hàm cần dùng
        * Sau đó ta tải ảnh lên và đưa về dạng list
        * Sau đó dùng hàm có sẵn để tính correlation coefficient và in ra.
    * Ứng dụng cho template mathching:
    ![](https://i.imgur.com/ErTlDb9.png)
        * Ví dụ ta có một hình lớn và một template sẵn có, ta sẽ tìm xem template ở đâu trong hình
        * Ý tưởng thực hiên: Ta sẽ cho template trượt trên hình và tính correlation coeffition. Sau đó với mỗi giá trị correlation coeffition ta lưu vào map. Thì giá trị của các điểm này có giá trị từ -1 đến 1.
        * Vùng nào có giá trị lớn nhất hay sáng nhất thì đó là vị trí của template
    ![](https://i.imgur.com/QA9wEjn.png)
    * Đầu tiên ta sẽ đưa ảnh về dạng ảnh xám
    * Và dùng hàm matchTemplate để tính correlation coeffition
    * Code để tim map:
    ![](https://i.imgur.com/M5C8Gpm.png)
    * Output:
    ![](https://i.imgur.com/ck5J3lq.png)
        * Vùng sáng nhất là vị trí template mình cần tìm.
        * Vì ảnh này khá là khó nhìn nên ta sẽ làm hình màu sắc hơn bằng một hàm trong openCV để hình dễ nhìn hơn. 
    ![](https://i.imgur.com/odibcEO.png)
    * Vùng có màu nóng nhất là vị trí template mình cần tìm
    * Trong hình là chỗ có màu đỏ
* Code để tìm template matching: 
    ![](https://i.imgur.com/0BlDFwY.png)
* Output cuối cùng: 
    ![](https://i.imgur.com/PpCcvkt.png)