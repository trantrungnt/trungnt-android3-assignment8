# trungnt-android3-assignment8
##Yêu cầu
+ [Xây dựng ứng dụng Nhận/Gửi tin nhắn: chuyển từ bài Assigment số 7 sang cách sử dụng Fragment](https://github.com/trantrungnt/trungnt-android3-assignment7)
+ Sử dụng Fragment để hiển thị gioa diện Danh sách Tin nhắn và Chi tiết 1 tin nhắn (2 Fragment frgListSMS và frgDetailSMS cùng nằm trong 1 vùng chứa Fragment => Khi click vào 1 tin nhắn thì chỉ có phần List SMS thay đổi sang giao diện frgDetailSMS; còn Action Bar giữ nguyên không đổi)

##Kiến thức sử dụng
+ Fragment là 1 mảnh nhỏ trong giao diện Android (nó cũng tương tự như 1 Activity nhưng chỉ là 1 mảnh nhỏ)
+ Có thể sử dụng FragmentManager class để quản lý Fragment (quản lý theo kiểu Stack, Fragment nào nằm đầu tiên trong FragmentManager thì được lấy lấy ra và xử lý đầu tiên)
+ Observer: giả sử trong giao diện MainActivity có chứa 2 Fragment frgListSMS và frgDetailSMS. Trong frgListSMS có chứa 1 Listview lvListSMS. Để click vào từng Item của ListView lvListSMS thì chỉ có mỗi Listview này cớ sự kiện click vào từng Item. Ở đây, ta mong muốn: click vào từng Item của ListView và chuyển sang từ frgListSMS sang frgDetailSMS, ta gọi sự kiện chuyển frgChuyenDoiFragment (phương thức frgChuyenDoiFragment này thực chất là dùng fragmentManager để lấy frgDetailSMS ra xử lý)


![BTVN-2742016-Receive/SendSMS](http://i477.photobucket.com/albums/rr132/trungepu/BTVN-242016-Receive-SendSMS_zpsvnsoforl.jpg)

##Môi trường phát triển

+ Mảy ảo AVD dùng Hệ điều hành Android api 21
+ Công cụ Android Studio verson 2.1
