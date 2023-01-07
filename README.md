# TCP/IP MODEL
### `Một bài viết về kiến thức cơ bản mô hình TCP/IP`
###### tags: Network
---
## TCP/IP Model là gì ?
TCP/IP (Transmission Control Protocol/Internet Protocol) là một trong các giao thức tiêu chuẩn trong môi trường mạng, được sử dụng để truyền dữ liệu hoặc các gói tin giữa các thiết bị được nối mạng với nhau.
Mô hình TCP/IP là một phiên bản ngắn gọn hơn của mô hình OSI gồm 4 tầng ==layer== hiện nay là 5 ==layer==. Vì là phiên bản thu gọn nên các chức năng của các tầng giữa 2 mô hình cũng khá giống nhau.
TCP/IP model là một mô hình được thiết kế để tiêu chuẩn hóa mạng máy tính theo các giao thức TCP và IP.
Hiện nay, TCP/IP model là mô hình phổ biến trên thế giới vượt xa Osi model.
## Layer 5: Application layer
- [ ] Tầng ứng dụng: đây là tập hợp của tầng 5, 6, 7 trong Osi Model.
> Tầng ứng dụng sẽ không xác định bản thân phần mềm sử dụng nó mà sẽ cung cấp các dịch vụ mà phần mềm cần. Ví dụ sẽ cung cấp giao thức HTTP cho các web browser có thể xuất ra nội dụng từ web server.
> Tầng 4 cung cấp một giao diện giữa phần mềm đang chạy trên máy tính với môi trường mạng trong chính nó.
> Hiện nay web browser chính là ứng dụng phổ biến nhất của TCP/IP 
- Các giao thức được sử dụng như HTTP, FTP, SMTP,..
## Layer 4: Transport layer
- [ ] Tầng vận chuyển: tương đương với tầng 4 trong Osi Model.
> Không giống với tầng ứng dụng tầng vận chuyển chỉ tập trung với 2 giao thức chính là TCP và UDP ==User Datagram Protocol==. 
> Tương tự như kiểm soát lỗi ==error control== ở Osi Model thì ở đây chúng ta có khôi phục lỗi ==error recovery==. Mỗi khi data được vận chuyển từ web server đến browser sẽ được gán thêm TCP header có số thứ tự ==sequence number (SEQ)==. Khi một SEQ bị mất thì phía browser sẽ yêu cầu web server gửi lại SEQ đó.
> Vì là tầng trung gian nên Transport layer sẽ có khả năng tương tác với các layer giống nhau và các layer liền kề ==Same-layer and Adjacent-layer Interaction==. Đối với giao tiếp Same-layer có thiết bị sử dụng cùng 1 giao thức để giao tiếp với nhau. Những giao thức này được xác định qua các header được thêm vào khi đi qua 1 layer.
>  Còn với Adjacent-layer thì chỉ thức hiện trên cùng một thiết bị, tầng thấp hơn sẽ cung cấp các dịch vụ mà chỉ có ở tầng dưới cho tầng phía trên nếu có yêu cầu. 
>  `Ví dụ HTTP muốn thực hiện error recovery sẽ phải yêu cầu TCP thực hiện error recovery`.
## Layer 3: Network layer
- [ ] Tầng mạng
> Mỗi thiết bị sử dụng TCP/IP - mỗi TCP/IP host cần một đại chỉ riêng để phân biệt nhau trong môi trường mạng. IP cũng xác định cách nhóm các địa chỉ lại với nhau.
> IP address là địa chỉ của thiết bị trong môi trường mạng ` ví dụ 1.1.1.1` Các IP address có cùng nhóm sẽ được kết nối với cùng 1 bộ định tuyến ==Router==. 
> Router là thiết bị mạng kết nối các phần của hệ thống mạng TCP/IP với mục đích vận chuyển ==routing== các IP packet tới vị trí chính xác. 
> Các router sẽ nhận IP packet thông qua các đường truyền vật lý khác nhau, xác định chúng dựa vào các IP header được thêm vào và vận chuyển chúng thông qua các đường truyền vật lý khác.
> IP header sẽ bao gồm địa chỉ nguồn và địa chỉ đến của IP packet.
> Các IP packet sẽ được vận chuyển qua các Router. Router sẽ xác định đâu là điểm đến của IP packet bằng việc so sánh IP address trong IP header với các IP Router khác mà nó biết. Công việc vận chuyện từ Router này đến Router khác gọi là Routing.
## Layer 2: Data-Link layer và Layer 1: Physical Layer.
- [ ] Trước đây thì 2 cái này là 1 nhưng hiện nay đã được tách ra như Osi Model.
> Đây là 2 tầng sẽ xác định các giao thức và phần cứng yêu cầu cho việc chuyển data thông qua đường truyền vật lý ==cables==. 
> Ở tầng 2 các data sẽ được thêm một ==frame header== và ==frame trailer== ở đầu và cuối data trước khi được dịch sang các bit ở tầng 1.
> Ở tầng 1 các bit được vận chuyển qua các tín hiệu điện thông qua ==cables==.

 