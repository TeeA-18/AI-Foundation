**GENETIC ALGORITHM**

**1. NP-Hard problem:**

   * Với một bài toán không thể mô phỏng hàm số f(x) bằng phương trình cụ thể
   * Cách giải:
        * One-max problem:
            * Cho một vector có chiều dài bằng 10, và ta có hai vector 1 và vector 2
            * Sau đó ta sẽ đánh giá vecto nào tốt hơn.
        ![](https://i.imgur.com/66JNQZE.png)
            * Hàm secret() bản thân thuật toán di truyền không biết. Thuật toán chỉ biết đầu vào là một vecto và đầu ra là một giá trị hay còn gọi là fitness()-giá trị để thể hiện độ tốt của vector, giá trị này càng lớn càng tốt.
        * Bài toán đặt ra:
            * Có vector v có độ dài bằng 10 và một vị trí nhận giá trị 0 hoặc 1 và có hàm secret. Hãy tìm vector v sao cho khi truyền vào hàm secret() thì ta sẽ có độ fitness cao nhất
        * Cách giải quyết:
            * Do các giá trị thuộc tâp [0,1] sau đó ta tạo m vector  bằng cách thả các giá trị ngẫu nhiên vào.

**2. Random search:**
    ![](https://i.imgur.com/OoJ6bQy.png)
    * Như ảnh trên ta sẽ tạo 8 vector ngẫu nhiên và đưa vào hàm secret() và ta sẽ có giá trị score tốt nhất là 6.
    * Example code:
            ![](https://i.imgur.com/jDyXl4J.png)
    * Chúng ta có thể quan sát hình dưới:
            * Phần màu xanh trung tâm là phần có giá trị fitness tốt nhất
            * Sau khi ta tính được giá trị fitness của 8 vector thì các giá trị của vector sẽ nằm giải rác như hình bên 
            * Để đạt được giá trị tốt nhất rất khó vị vùng không gian tìm kiếm là vô tận
         ![](https://i.imgur.com/cANaegR.png)
    * Khi chúng ta tính càng nhiều vector thì các giá trị sẽ càng phủ kín vùng searching space và ta có cơ hội tìm ra điểm tốt nhất
    * Nhưng có mốt vấn đề xảy ra đó là chúng ta sẽ không đủ tài nguyên máy tính đế làm việc đó khi tăng số lượng vector lên
        ![](https://i.imgur.com/HuNEX7p.png)
    * Để thuật toán chạy ổn định và có giá trị fitness tốt thì ta sẽ dùng cách khác cách trên đó là:
        * Cứ sinh ra 8 vector là tối đa(ví dụ) thì ta có thể sinh ra 8 vector nhiều lần và giữ lại giá trị fitness tốt nhất sau mỗi lần sinh.

**3. Genetic algorithm:**
* Thuật toán này được lấy cảm hứng của thuyết tiến hóa trong darwin.
    ![](https://i.imgur.com/e61f1rd.png)
    * Một vị trí trong vector đước gọi là gene
    * Một vector được gọi là một cá thể hay là Chromesome
    * M vector thì được gọi là 1 quần thể hay population.
    * Khi mình muốn viết một bài báo về giải thuật di truyền thì phải dùng các từ ngữ chuyên ngành như trên.
* Các bước tổng quát của thuật toán genetic:
    ![](https://i.imgur.com/vlOLV2A.png)
* Population Initialization: 
    * Đầu tiên ta tạo ra 10 cá thể có độ dài bằng 5 như hình sau:
    ![](https://i.imgur.com/S2L2Dqo.png)
* Evaluation:
    * Đầu vào input của bước này là một quần thể và lấy từng cá thể vào hàm secret() để chạy lấy output:
    ![](https://i.imgur.com/v1Cq6sb.png)
* Selection:
    * Ví dụ mình có một quần thể và đã biết giá trị fitness của một cá thể.
    * Ý nghĩa của bước này là những cá thể nào có giá trị fitness tốt nhất thì được ưu tiên trọn nhiều hơn.
    * Đôi khi cá thể có giá trị fitness nhỏ nhất chưa chắc đã vô dụng vì đôi khi nó có những gene đặc biệt mà các cá thể khác không có
    * Chúng ta chọn hết những cái có giá trị fitness tốt và vứt hết những cái nhỏ thì đôi khi không phải là tốt vì đôi khi đó là giá trị cục bộ
    * Có nhiều phương pháp selection nhưng trong ví dụ này ta sẽ dùng phương pháp binary selection:
        * Lấy random 2 cá thể và chọn cá thể nào có độ fitness tốt hơn đến khi đủ một quần thể thì thôi, sau đó ta có output như sau:
        ![](https://i.imgur.com/N4zRbcU.png)
        * Example code:
        ![](https://i.imgur.com/Os5N754.png)
* Crossover:
    * Binary crossover:
        * Đầu tiên ta sẽ sinh ra một vector ngẫu nhiên với tỉ lệ crossove rate là 90%
        * Tỉ lệ 90% nghĩa là ta sinh con số từ ngẫu nhiên từ 0 đên 1. Số nào nằm trong khoảng 0 - 0.9 sẽ nhận giá trị true còn lại sẽ nhận giá trị false.
        ![](https://i.imgur.com/QzQCqDW.png)
        * Chỗ nào có giá trị True thì sẽ thực hiện crossover hay trao đổi gen
        * Chỗ nào có giá trị False thì sẽ giữ nguyên
        * Example code:
        ![](https://i.imgur.com/LqZYY9i.png)
* Mutation:
    * Ta cũng dùng mutation rate nhưng tỉ lệ rất hấp 0.05(đột biến)
    * Chố nào có giá trị True thì ta sẽ sinh ra một giá trị ngẫu nhiên chứ không phải thay đổi giá trị của gene
    ![](https://i.imgur.com/lCDY84b.png)
    * Example code:
    ![](https://i.imgur.com/GY5IAkQ.png)
* Tổng hợp các hàm trên lại vào một method:
    ![](https://i.imgur.com/LGjDRe1.png)
    * Sau đó chạy ta có output như sau:
    ![](https://i.imgur.com/FSOLlpf.png)
* Elitism:
    * Trước khi tạo population mới mình lấy vector tốt nhất của population cũ qua có thể 1,2,3 vector.
    * Và cuối cùng ta output biểu diễn qua ảnh:
    ![](https://i.imgur.com/aUUYC2p.png)
