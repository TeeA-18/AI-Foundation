**PYTHON**
**1 Variable:**
* Ta có 4 kiểu dữ liệu cơ bản(nguyên thủy) trong python:
    ![](https://i.imgur.com/fcXFPm0.png)
* Ta có thể khải báo biến trong python chỉ cần tên biến và gán giá trị và không cần khai báo kiểu
    ![](https://i.imgur.com/wLxdKAe.png)
* Trong python thì ta sẽ có một vài từ key word quan trọng và không thể dùng để đặt tên biến
    ![](https://i.imgur.com/yay98UZ.png)
* Trong python sẽ có một vài hàm có sẵn và ta chỉ cần gọi để dùng
    ![](https://i.imgur.com/uA1RFNA.png)
    * Hàm trên sẽ in ra giá trị của biến truyền vào
    ![](https://i.imgur.com/9rqjEMD.png)
    * Hàm trên sẽ in ra output kiểu của biến truyền vào
* Type Conversion:
    * Ta dùng type conversion để ép kiểu của biến - hay thay đổi kiểu dữ liệu của biến
        * Ví như như khi ta nhập số tuổi của bạn từ bạn phím thì dữ liêu được nhập vào sẽ cos kiểu String
        * Sau đó ta sẽ dùng type conversion để ép biến số tuổi sang kiểu int để xử lý
        ![](https://i.imgur.com/epLmY6F.png)
* Ta có một số operator để thực hiện các phép tính toán trong python như bảng sau:
    ![](https://i.imgur.com/HFcMctC.png)
**2 Function:**
* Có những lưu ý sau đây khi ta xây dựng một hàm trong pyton
    * Khai báo tên của hàm: dùng chữ viết thường và dấu underscores để ngăn cách các từ
    * Chúng ta phải thụt vào lề 4 khoảng trắng khi viết thân hàm
    * Xác định tham số truyền vào hàm để xử lí
    * Viết miêu tả hàm
    ![](https://i.imgur.com/ys7tcyS.png)
* Ta có những phép toàn tử để so sánh trong python như bảng sau:
    ![](https://i.imgur.com/rMogBU9.png)
**3 If condition:**
![](https://i.imgur.com/Mi2cQYn.png)
* Nếu điều kiện trong đang xét đúng thì sẽ thực hiến khối code trong if
* Câu if else:
    ![](https://i.imgur.com/uNdhjGM.png)
* Đầu tiên sẽ sét xem điều kiện trong if có đúng hay không, nều đùng thì thực hiện khối code trong if, nếu không thực hiện khôi code trong else

**4 For condition:**
![](https://i.imgur.com/ADncTys.png)
* Đầu tiên sẽ cần dùng iterable trong vòng for để xét duyệt xem đã đến phần tử cuối cùng trong iterable chưa:
    * Nếu chưa thì sẽ thực thi câu lệnh trong for
    * Nếu rồi thì sẽ thoát ra vòng for và thực thi câu lệnh sau for
    * Iterable có thể là String , tuple, list, dictionary, range()
    * Hàm range() có 3 tham số truyền vào:
        * start = 0, stop, step = 1, lấy các số bắt đầu từ start , kết thúc ở stop và có khoảng cách là step
        ![](https://i.imgur.com/vMYXNJm.png)
        * Nếu ta chỉ truyền một số vào hàm thì nó sẽ loại bỏ các giá trị mặc định và stop sẽ nhận giá trị bằng 5
    * Keyword break dùng để thoát ra khỏi vòng lặp
    * Keyword continue dùng để bỏ qua đoạn code ở sau từ continue nhưng vẫn tiếp tục vòng lặp cho đến hết
**5 While loop:**
* Đây sẽ là mô hình mà vòng lặp while hoạt động:
    ![](https://i.imgur.com/Tk0HFJR.png)
    * Đầu tiên sẽ xét condition trước, nếu condition vẫn đúng thì thực hiện khối code trong while nếu sai sẽ thoát khỏi vòng while và thực hiện các dòng code còn lại
    * Chú ý rằng nếu condition còn đúng thì vẫn sẽ thực hiện khối code trong while:
        * Ta có thể dùng while(true) để tạo một vòng lặp vô hạn và sau đó có thể dùng keyword break để thoát ra
**6 List:**
* List giống một container có thể lưu trữ các phần tử
* Chúng ta có thể khai báo một list bằng cách:
    * Viết tên list rồi gán giá trị cho các phần tử trong dấu "[]" và ngăn cách bằng dấu ","
    ![](https://i.imgur.com/KFnT7zS.png)
* Index dùng để chỉ mục và đánh số các phần tử của list , giúp dễ dàng trong việc truy xuất để xử lý
    * Index bắt đầu từ số 0 - tương ứng với phần tử đầu tiên
![](https://i.imgur.com/51qnqOT.png)
    * Ngoài ra còn backward index bắt đầu từ -1 - tương ứng phần tử lớn nhất sau đó giảm dần
![](https://i.imgur.com/t3Oq09W.png)
* Chúng ta dùng slicing để truy xuất các phần tử của list theo khoảng 
    * Ví dụ [2:4] sẽ lấy ra phần tử có giá trị index từ 2 đến 4
    * Ví dụ như trong ành 
    ![](https://i.imgur.com/314OdrJ.png)
* Chúng ra dùng hàm append() để chèn thêm các phần tử vào trong list
    * Nếu ta truyền vào một tham số thì hàm append sẽ hiều là thêm giá trị này vào cuối của list
    * Nếu truyền vào hai giá trị thì giá trị đầu sẽ được xác định là vị trí thêm phần tử còn giá trị sau là giá trị cần thêm
    ![](https://i.imgur.com/lL1quOQ.png)
* Nếu muốn update element vì chúng ta chỉ cần truy xuất phần tử chúng ta muốn thay đổi bằng giá trị index sau đó gán giá trị muốn update:
    ![](https://i.imgur.com/tjrYIoK.png)
* Ta dùng dấu "+" để nối hai list với nhau:
    * Ví dụ data1 = [6,5,7] ; data2 = [1,9,2] thì data1 + data2 =
    ![](https://i.imgur.com/6YdPLDz.png)
* Ta dùng dấu "*" để nhân giá trị của một list với một số nguyên nào đó
* Hàm sort() giúp ta sắp xếp các phần tử trong list theo chiều tăng dần 
    ![](https://i.imgur.com/R4ijUJH.png)
* Muốn xóa phần tử trong list ta có thể dùng hai hàm pop() và remove()
    * Hàm pop(a) sẽ xóa phần tử có giá trị index là a
    * Hàm remove(a) sẽ xóa phần tử có giá trị là a
    * Chúng ta có thể dùng hàm clear() để xóa hết với các phần tử trong mảng
* Ta dùng hàm index(a) để trả về giá trị index của phần tử a đầu tiên trong list
* Ta dùng hàm count(a) để đếm số lần xuất hiện của phần tử a trong list
* Ta dùng hàm reverse() để đảo ngược vị trị của các element trong list:
    ![](https://i.imgur.com/pKOd7AM.png)
* Ta dùng hàm copy() để copy một list rồi gán cho list khác 
* List comprehension
![](https://i.imgur.com/MkRDcmk.png)
    * Đầu tiên sẽ xét biểu thức expression với các giá trị trong iterable, nếu đúng thì sẽ được thêm vào list
    
**7 Data type:**
*    Chúng ta sẽ có hai kiểu dữ liệu là immutable và mutable
![](https://i.imgur.com/zBtaBKe.png)
* Dữ liệu kiểu immutable thì khi vùng nhớ đã tạo ra rồi, không thay đổi được
* Nếu muốn thay đôi thì phải tạo vùng nhớ mới để lưu trữ
* Còn data kiểu mutable thì có thể thay đổi được mà không cần tạo vùng nhớ mới  

**8 String:**
* String trong python là một mảng byte đại diện cho các ký tự unicode
* Các chuỗi kí tự trong python được bao quanh bởi dấu ngoặc kép hay ngoặc đơn
* Các hàm phổ biến trong String:
    * isdigit(): Kiểm tra xem String gồm các kí tự số hay không
     ![](https://i.imgur.com/mdkf9s4.png)
    * islower(): Kiểm tra xem String có phải là các chữ thường hay không
    ![](https://i.imgur.com/NOOKYkM.png)
    * isalpha(): Kiểm tra xem String có phải đếu là chữ cái hết hay không
    ![](https://i.imgur.com/01YKghI.png)
    * isupper(): Kiểm tra xem String có phải đều là chữ viết hoa hay không
    ![](https://i.imgur.com/YAMOMh3.png)
    * istitle(): Kiểm tra xem String có phải bắt đầu bằng chữ hoa hay không
    ![](https://i.imgur.com/h6ncdWW.png)
    * count() đếm số lần xuất hiện của một kí tự, len() để tính chiều dài của String
    ![](https://i.imgur.com/ezhM1IQ.png)
    * isspace() kiểm tra xem String có phải là khoảng trắng hay không
    ![](https://i.imgur.com/k4e4GCD.png)
**9 Tuple:**
* Tuple là một collection được sắp xếp theo thứ tự và không thể thay đổi
* Các bộ giá trị được viết trong dấu ngoặc tròn
![](https://i.imgur.com/qslh33b.png)
* Có thể truy cập được các items của tuple bằng cách truy xuất đến số chỉ mục bên trong dấu ngoặc vuông

**10 Set:**
* Set là một collection không có thứ tự và không được đánh sô index cho mỗi phần tử
* Set được viết với dầu ngoặc nhọn
![](https://i.imgur.com/5qOZKob.png)
* Bạn không thể truy cập các phần tử của set bằng cách tham chiếu đến index hay key
* Bạn có thể truy cập các phần tử bằng cách dùng vòng lặp
![](https://i.imgur.com/81VnjY9.png)
* Dưới đây là một số hàm hay sử dụng trong set:
![](https://i.imgur.com/o5DSujf.png)
**11 Dictionary:**
* Dictionary là một collection không có thứ tự, có thể thay đổi và được lập chỉ mục
* Được viết trong dấu ngoặc nhọn với các key và value
![](https://i.imgur.com/guj3FA6.png)
* Chúng ta có thể sử dụng key để update value
![](https://i.imgur.com/daPtDDb.png)
* Cách để lấy key và value trong dictionary:
![](https://i.imgur.com/jvP4xDR.png)
* Một số hàm trong dictionary:
    * popitem() đễ xóa item ở cuối dictionary
    ![](https://i.imgur.com/3n8V6Wa.png)
    * clear() để xóa tất cả phần tử của dictionary 
    ![](https://i.imgur.com/cdiovCd.png)
**12 File:**
* Hàm quan trọng để làm việc với file trong python là open()
* Hàm open lầy 2 giá trị tham số là filename và mode
* Có 4 method khác nhau dựa vào mode trong python
![](https://i.imgur.com/vxOY9pa.png)
* Cách viết thêm nội dung vào file có sẵn:
![](https://i.imgur.com/hpLvskz.png)
* Chúng ta dùng hàm open và truyền vào tham số là file cần thao tác và mode là a để append thêm nội dung file
* Sau đó dùng hàm write() để viết nội dung vào file
* Dùng hàm close() để đóng file
* Example code và output:
![](https://i.imgur.com/y87Agyn.png)