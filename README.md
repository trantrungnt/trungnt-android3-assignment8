# trungnt-android3-assignment8
##Yêu cầu
+ [Xây dựng ứng dụng Nhận/Gửi tin nhắn: chuyển từ bài Assigment số 7 sang cách sử dụng Fragment](https://github.com/trantrungnt/trungnt-android3-assignment7)
+ Sử dụng Fragment để hiển thị gioa diện Danh sách Tin nhắn và Chi tiết 1 tin nhắn (2 Fragment frgListSMS và frgDetailSMS cùng nằm trong 1 vùng chứa Fragment => Khi click vào 1 tin nhắn thì chỉ có phần List SMS thay đổi sang giao diện frgDetailSMS; còn Action Bar giữ nguyên không đổi)

##Kiến thức sử dụng
+ Fragment là 1 mảnh nhỏ trong giao diện Android (nó cũng tương tự như 1 Activity nhưng chỉ là 1 mảnh nhỏ)
+ Có thể sử dụng FragmentManager class để quản lý Fragment (quản lý theo kiểu Stack, Fragment nào nằm đầu tiên trong FragmentManager thì được lấy lấy ra và xử lý đầu tiên)
+ Chỉ sử dụng Fragment khi dữ liệu tương đồng: kiểu dạng như dữ liệu tin nhắn. dữ liệu làm bài trắc nghiệm (từ danh sách các câu hỏi trắc nghiệm, khi click từng Item câu hỏi thì chuyển sang fragment có chứa câu hỏi được chọn và danh sách các đáp án) ... Riêng dữ liệu kiểu dạng như: Employee (từ danh sách Employee, ta click chọn vào 1 item thì hiện ra thông tin chi tiết của Nhân viên đó: để bảo mật thông tin dữ liệu thì nên dùng 2 Activity là: ListEmployeeActivyt và DetailEmployeeActivity để đảm bảo chuyển đổi dữ liệu giữa các Activity sẽ được bảo mật dữ liệu hơn)
+ ObServer: giả sử trong giao diện MainActivity có chứa 2 Fragment frgListSMS và frgDetailSMS. Trong frgListSMS có chứa 1 Listview lvListSMS. Để click vào từng Item của ListView lvListSMS thì chỉ có mỗi Listview này cớ sự kiện click vào từng Item. Ở đây, ta mong muốn: click vào từng Item của ListView và chuyển sang từ frgListSMS sang frgDetailSMS, ta gọi sự kiện chuyển frgChuyenDoiFragment (phương thức frgChuyenDoiFragment này thực chất là dùng fragmentManager để lấy frgDetailSMS ra xử lý). Hiện tại, frgListSMS và MainActivity "không thể gọi phương thức clickOnItem của Listview" nên ta phải dùng Obser ở trường hợp này. Nghĩa là: ta sẽ định nghĩa 1 ObServer chuyên làm 1 nhiệm vụ là chuyển Fragment (chuyển từ Fragment frgListSMS sang frgDetailSMS) trong FragmentListSMS. Tiếp theo, MainActivity sẽ được implement ObServer với phương thức void frgChuyenDoiFragment(). Tại đây, MainActivity đã được implement Observer có 1 phương thức void frgChuyenDoiFragment chuyển làm nhiệm vụ chuyển đỗi giữa các fragment: mỗi lần click vào từng Item trên ListView, MainActivity sẽ thực hiện được việc chuyển đổi 2 fragment: frgListSMS và frgDetailSMS. 
Ta có thể hiểu đơn giản ObServer với kiến thức thực tế của con người: 1 Person có nhiều khả năng như: đi, ngủ, chạy, nói. Ở trường học thì có Student với phương thức là Learn, ở nhà thì có Con cái với phương thức là Nghe Lời, ở Công ty thì có Nhân viên với phương thức là Làm việc, Khi ta cài đặt ObServer cho 1 Person có thêm phương thức Learn thì người đó sẽ có phương thức Leanr. Vậy khi ở trường, 1 Person sẽ là 1 Student và có phương thức Learn. 


![BTVN-2742016-Receive/SendSMS](http://i477.photobucket.com/albums/rr132/trungepu/BTVN-242016-Receive-SendSMS_zpsvnsoforl.jpg)

##Môi trường phát triển

+ Mảy ảo AVD dùng Hệ điều hành Android api 21
+ Công cụ Android Studio verson 2.1
