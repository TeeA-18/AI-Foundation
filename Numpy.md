**NUMPY**

*1 Introduction: * 
* Numpy arrays là một mảng đa chiều
* Mình có thể định nghĩa số chiều như trong ảnh sau:
    ![](https://i.imgur.com/FHFTMDt.png)

* Cách tạo một numpy array sử dụng list: 
    * np. để gọi hàm trong numpy
    ![](https://i.imgur.com/rz2htrH.png)

* Các attributes 
    * dtype: trả về kiểu của dữ liệu
    * shape: trả về một tuple số chiều của mỗi phần tử
        * Ví dụ shape=(3,) thì array có số chiều bằng 1 và độ dài bằng 3
    * ndim: trả về số chiều 
    

    
* Update một phần tử
    * Ví dụ tạo ra một cái array data có 1 chiều và độ dài bằng 3:
    * muốn update phần tử ở vị trí index nào đó ta dùng: data[index] = value
     ![](https://i.imgur.com/3PqF7op.png)

* Tạo một array:
    * Ta dùng hàm zeros((x,y)) để tạo một cái array toàn số 0 trong đó x là số chiều còn y là độ dài một chiều
    ![](https://i.imgur.com/LfEcJE9.png)

    * Ta dùng hàm ones() function để tạo ra một array toàn số một
    ![](https://i.imgur.com/4cYUkgn.png)

    * Ta dùng hàm full((x,y), z ) để tạo một array có x chiều , chiều dài mỗi chiều là y và có tất cả giá trị của array đều là z
    ![](https://i.imgur.com/foby5jl.png)
    * Ta dùng hàm arrange(start=0,stop,step=1)
        * Khi truyền vào một giá trị np.arrange(5) thì nó sẽ bỏ qua những giá trị mặc định và xác đình stop = 5 sau đó in ra
        * Khi truyền vào 3 giá trị np.arrange(0,5,2) thí nó sẽ xác định stop = 0, stop = 5, step = 2 sau đó in ra
        ![](https://i.imgur.com/ZH0qHgH.png)

    * Ta dùng hàm eye() để tạo một numpy array với đường chéo bằng 1 còn các phần tử còn lại được điền giá trị 0:
        * Khi ta truyền giá trị 3 vào np.eye(3) thì nó sẽ hiểu 3 là số hàng vá số cột say đó in ra:
        ![](https://i.imgur.com/JSMtQsr.png)

    * Ta dùng hàm random() để tạo một numpy array với các giá trị ngẫu nhiên
        * Khi ta truyền giá trị vào np.random.random((2,3)) thì nó sẽ tạo ra một array với 2 hàng và 3 cột với các giá trị ngẫu nhiên
    ![](https://i.imgur.com/4Fmx7TA.png)

* Một số hàm quan trọng:
    * where(condition, arr, arr*2) function thì condition là điều kiện mà người dùng tạo ra, arr là hàm truyền vào để xử lý. 
        * Nếu các phần nào thỏa mãn điều kiện thì giữ nguyên, còn false thì sẽ thực hiện điều kiện thứ 3(arr*2)
        ![](https://i.imgur.com/6dNtHoh.png)

    * Mọi thứ trong numpy thì đều được xử lý dựa vào vector chứ không lấy từng phần tử ra để xử lý
    * flatten() function dùng để kéo các mảng nhiều chiều thành một mảng một chiều
    ![](https://i.imgur.com/3K1zHtT.png)

    * Ta dùng reshape function để đổi ma trân x dòng y cột thành ma trận y dòng x cột
    ![](https://i.imgur.com/fZ3r4S3.png)

*2 Array indexing*
* Slicing
    * Công thức như trong hình
    ![](https://i.imgur.com/cZAFgcf.png)  
    * Dầu ":" không có nghĩa là lấy hết, giá trị bắt đầu là số chiều thứ nhất và giá trị kết thúc là số chiều thứ hai
    * a:b nghĩa là lấy phần tử từ a đến b 
    
* Get a row:
    ![](https://i.imgur.com/ZPAZ3tM.png)
* Get a column:
    ![](https://i.imgur.com/zPr3u24.png)
* Using Lists as indices:
![](https://i.imgur.com/FF5LPyQ.png)    

*3 Array operators:*
* Addition:
    * Khi cộng hai array chúng ta chỉ cần cộng tương ứng các phần tử
    ![](https://i.imgur.com/NduEFJw.png)

    * Thay vì dùng hàm np.add(x,y) ta có thể dùng x + y
* Subtraction:
    * Khi trừ hai array chúng ta cũng trừ tương ứng các phần tử ở hai vector
    ![](https://i.imgur.com/nClFZOH.png)

* Multiplication:
    * Khi nhân hai array tương tự ta cũng nhân hai phần tử tương  ứng ở vector 
    ![](https://i.imgur.com/VSXuEYj.png)

* Division:
    * Khi dùng dấu / thì kết quả sẽ lấy phần dư
    * Còn khi dùng hai dấu // sẽ trả về phần nguyên 
    ![](https://i.imgur.com/khci1sZ.png)

* Square root:
    * Ta dùng hàm np.sprt(data) để tính căn của từng phần tử trong array
    ![](https://i.imgur.com/eTnZWs2.png)

* Inner product:
    * Tích chập của hai array: Ta nhân tương ứng các phần tử của hai aray rồi cộng lại 
    * Ví dụ có hai array v và w, ta có hai cách dùng hàm này
        * v,dot(w)
        * np.dot(v,w)
       ![](https://i.imgur.com/zZtQnJH.png) 

* Vector-matrix multiplication:
    * Ta nhân một vector với một ma trận 
    ![](https://i.imgur.com/csPxSRe.png)

* Matrix-matrix multiplication:
    * Ta nhân một ma trận với một ma trận
    ![](https://i.imgur.com/66s96bl.png)
    * Ma trận không có tính hoán vị
    ![](https://i.imgur.com/BNSX69w.png)

* Transpose:
    * Cho một ma trận nếu tao muốn đổi dòng thành cột thì ta có thể dùng hàm X.T(X là array cần hoán vị)
    ![](https://i.imgur.com/3DLsQ3e.png)

* Summation:
    * Ta muốn tính tổng các phần tử của một array ta dùng hàm np.sum()
    ![](https://i.imgur.com/W6UoTFW.png)
    * Ta muốn tính tổng các phần tử theo cột thì dùng hàm np.sum(X, axis = 0)
    ![](https://i.imgur.com/VqrlGbz.png)
    * Ta muốn tính tổng các phần tử theo hàng thì dùngh àm np.sum(X,axis = 1)
    ![](https://i.imgur.com/PbMBIKg.png)
* Max and min
    * Ta dùng hàm .max() để in ra giá trị lớn nhất của array
    ![](https://i.imgur.com/N3ydiGD.png)

    * Ta dùng hàm .min() để in ra giá trị nhỏ nhất của array
    ![](https://i.imgur.com/9UcMA1Y.png)

*3. Broadcasting:*
* Matrix and vector:
    * Vector and scalar:
    ![](https://i.imgur.com/R7Q5iSq.png)
    * Khi cộng matrix với vector nó sẽ nội suy vector rồi mới cộng với matrix như ảnh sau:
    ![](https://i.imgur.com/Xm3YIa4.png)
