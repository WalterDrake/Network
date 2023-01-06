# OSI Model

[![hackmd-github-sync-badge](https://hackmd.io/fxHf-JxVSfi-F3C61j60Ow/badge)](https://hackmd.io/fxHf-JxVSfi-F3C61j60Ow)

### `Một bài viết về kiến thức cơ bản của mô hình OSI`
###### tags: Network
---
## Osi model là gì ?
Osi model `(Open Systems Interconnection Model)` là một trong những mô hình cơ bản về hệ thống mạng. Đây là một mô hình cung cấp một khuôn khổ chung về cách data được gửi đi, nhận lại và thông dịch.
Một trong những lợi ích của mô hình OSI là cung cấp khả năng giao tiếp theo một tiêu chuẩn chung giữa những thiết bị mạng có chức năng và thiết kế khác nhau.
Osi model được chia thành 7 tầng `layer`. Đi từ `layer 7 → layer 1`. Mỗi `layer` chịu trách nhiệm cho một chức năng khác nhau.
Khi đi xuống 1 layer hay đi lên data sẽ được gán thêm hoặc bỏ ra 1 header vào được gọi là hình thức đóng gói và mở gói của data ==data encapsulation== ==data De-encapsulation==.
Ngày nay Osi model không còn được sử dụng quá phổ biến vì quá trình tiêu chuẩn hóa diễn ra chậm hơn so với TCP/IP model. 
## Layer 7: Application layer 
- [ ] Tầng ứng dụng
 
> Đây là tầng duy nhất mà con người và máy tính tương tác qua lại với nhau. Nơi các thiết bị có thể truy cập các dịch vụ mạng. Các ứng dụng như giao diện email hay các giao diện web ==(GUI)== sử dụng nó để bắt đầu truyền data. Tầng 7 chịu trách nhiệm về giao thức và các thao tác dữ liệu. Các ứng dụng dựa vào nó để thể hiện data tới người dùng.
- Giao thức được sử dụng như HTTP,DNS,...
## Layer 6: The presentation layer
- [ ] Tầng trình diễn (:> cái tên nghe hơi sú )
> Tầng trình diễn là nơi các tiêu chuẩn hóa được xảy ra. Đây là cửa vào đầu tiên hoặc cửa ra cuối cùng của data trước khi được truyền đi hoặc xuất ra. Vì tầng 7 là nơi duy nhất mà con người có tương tác với data => tầng 6 đóng vai trò như một người phiên dịch. Chức năng của tầng 6 là mã hóa, nén data trước khi đi vào tầng 5 hoặc giải mã, giải nén data khi đi ra tầng 7.
- Các thiết bị có thể hiểu nhau dù sử dụng các phương thức mã hóa khác nhau do tầng 6 có khả năng chuyển các ký tự mã hóa của data đến thành các ký tự mà tầng ứng dụng của máy nhận có thể hiểu được.
- Ở giao thức HTTPS hoặc các kết nối có mã hóa, tầng 6 có chức năng mã hóa các data khi người gửi kết thúc và dịch các data đã bị mã hóa ở phía người nhận.
- Tầng 6 còn có chức năng nén data trước khi đi vào tầng 5. Điều này giúp tăng tốc độ và hiệu quả của data được truyền đi.
## Layer 5: Session layer 
- [ ] Tầng phiên 
>Đây là tầng mở ra kết nối giữa 2 thiết bị. Khi data từ tầng 6 đã được mã hóa và nén xong, tầng 5 sẽ bắt đầu tạo ra kết nối tới nơi data cần đến. Khoảng thời gian giữa đóng và mở khi kết nối giữa 2 thiết bị được gọi là 1 phiên ==session==. Tầng 5 đảm bảo rằng các session được mở ra đủ thời gian để các data giữa 2 thiết bị trao đổi với nhau, và đóng lại session khi kết thúc tránh lãng phí tài nguyên.
- Một trong những khả năng của tầng 5 là đồng bộ hóa data được vận chuyển bằng các điểm lưu ==checkpoint==. Data sẽ được phân chia thành nhiều và sẽ được gửi đi cùng một lúc. Việc phân chia giúp cho việc khi mất kết nối giữa 2 thiết bị, các data chưa được gửi đi từ checkpoint cuối sẽ được tiếp tục gửi đi thay vì phải gửi lại toàn bộ.
- Các session là duy nhất, data không thể đi qua các session khác nhau mà chỉ đi qua từng session một.
- Giao thức được sử dụng như TCP.
## Layer 4: Transport layer
- [ ] Tầng vận chuyển
> Tầng vận chuyển chịu trách nhiệm cho việc giao tiếp đầu cuối giữa 2 thiết bị. Nó lấy các data từ tầng 5 thêm ==segments header==  vào trước khi được gửi vào tầng 3. Ở thiết bị nhận tầng 4 có vai trò gỡ bỏ các ==segments header== từ thiết bị gửi chuyển đến. 
- Kiểm soát luồng có mục đích xác định tốc độ tối ưu cho việc trao đổi đảm bảo người gửi có một kết nối nhanh không làm quá tải người nhận có kết nối chậm.
- Kiểm soát lỗi được thực hiện trên thiết bị nhận khi kết thúc, đảm bảo data nhận vào là hoàn tất và yêu cầu gửi lại nếu không hoàn thành.
- Giao thức được sử dụng như TCP, UDP.
## Layer 3: Network layer
- [ ] Tầng mạng
> Tầng 3 chịu trách nhiệm cho việc hỗ trợ truyền dữ liệu giữa 2 thiết bị ngoại mạng. Nếu 2 thiết bị giao tiếp trên cùng 1 mạng thì tầng 3 là không cần thiết. Tầng 3 sẽ được thêm các ==packet header== trên thiết bị gửi và gỡ bỏ trên thiết bị nhận.
- Tầng 3 còn có chức năng sẽ tìm đường dẫn vật lý tối ưu nhất cho data được gửi đi.
- Các thiết bị ở tầng 3 như ==routers== vận chuyển các ==packet== qua các ==IP addresses==.
- Giao thức được sử dụng như IP.
## Layer 2: Data-Link layer
- [ ] Tầng liên kết dữ liệu
> Có chức năng tương tự với tầng 3, ngoại trừ việc nó sử dụng trong cùng một mạng. Tầng 2 sẽ có 2 header được thêm vào là ==frame header== nằm ở phía đầu data và ==frame trailer== nằm ở phía cuối data. Giống như tầng 3, tầng 2 cũng có khả năng kiểm soát luồng và kiểm soát lỗi trong mạng nội bộ ==intranet==.
`Transport layer chỉ kiểm soát luồng và lỗi ở mạng internet`.
- Ở tầng 2 các frame được vận chuyển thông qua địa chỉ MAC trên máy hoặc switch.
- Giao thức được sử dụng Ethernet.
## Layer 1: Physical layer
- [ ] Tầng vật lý
> Tầng này bao gồm các thiết bị vật lý có liên quan đến việc vận chuyển data như dây cáp ==cables== và ==hubs==. Ở tầng 1 data sẽ được dịch sang các dòng bit. Cả 2 thiết bị vật lý gửi và nhận của tầng 1 phải có chung các quy ước về tín hiệu để hiểu nhau.
### Tài liệu tham khảo: 
[Link](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)
[Link](https://www.cloudflare.com/learning/network-layer/what-is-the-network-layer/#:~:text=Network%20layer%3A%20Handles%20the%20routing,devices%20on%20the%20same%20network.)
![](https://i.imgur.com/5B3ZlLN.png)
![](https://i.imgur.com/Tc2iQnc.png)



