QUẢN LÝ ĐỖ XE Ô TÔ

1. Mô tả: Các toà nhà cần 1 hệ thống quản lý đỗ xe ô tô, cho phép người quản lý kiểm soát thông tin khu vực đỗ xe cũng như người dùng có thể chọn được chỗ đỗ xe gần nhất. Hệ thống chỉ phục vụ người dùng có đăng ký gửi xe hợp lệ được  phép đặt trỗ trước khi vào khu vực gửi xe thông qua web app (hỗ trợ mobile). Nếu chỗ đỗ xe được đặt nhưng ko đc sử  dụng trong 1 khoảng thời gian nhất định thì hệ thống sẽ tự động huỷ đặt chỗ ở vị trí đó để xe khác có thể đặt. 

2. Tính năng: 
 - Hệ thống có 2 giao diện cho 2 kiểu người dùng (user và admin) 
 - Admin page cho phép người quản trị cấu hình thông số khu vực đỗ xe theo slot hàng và cột (ví dụ 10 * 10 chỗ đỗ xe). Các slot sẽ theo thứ tự từ trái sang phải, từ, trên xuống dưới. Các slot cần có tên (ví dụ S1, S2, … hoặc đơn giản là 1, 2,  …) 
 - Admin page cũng cho phép người quản trị theo dõi thông tin người dùng đăng ký gửi xe kèm trạng thái của người  dùng đó là `active` hay `inactive`. Chỉ có những active user mới được phép đặt chỗ đỗ xe. Admin có thể thay đổi trạng  thái này. 
 - Home page cho phép hiển thị các slot đỗ xe, phân biệt được slot còn trống và đã có người sử dụng, hiển thị tổng số  chỗ đỗ xe còn trống. 
 - Tính năng đặt chỗ đỗ xe trên Home Page phải tự động suggest vị trí đỗ xe gần nhất cho người dùng. (Vị trí gần nhất  là vị trí đầu tiên còn trống theo thứ tự ưu tiên ở trên - trái sang phải, trên xuống dưới) 
 - Admin có thể giải phóng slot đỗ xe trên Home Page như việc người dùng đã lấy xe ra khỏi bãi đỗ.  
 - Hệ thống KO yêu cầu realtime vì vậy mọi hành động ko thành công cần được xử lý. Ví dụ khi slot bị người khác đặt  trước khi submit thì cần show thông báo và chuyển suggest sang vị trí tiếp theo 
 - Sau khi đặt chỗ thành công, sẽ có countdown (thời gian countdown được cấu hình bởi admin). Hành động `Park`  được thực hiện trước khi hết giờ sẽ đảm bảo chỗ đỗ xe được sử dụng. Nếu ko sẽ tự động huỷ đặt chỗ cho vị trí đó. 
Lưu  ý: hành động này thực hiện ở phía client nên bỏ qua trường hợp thoát khỏi trang, nghĩa là nếu người dùng thoát khỏi khu  vực quản lý action countdown thì coi như `Park`. 

3. Tech stack: React + … Không giới hạn việc sử dụng công nghệ, thư viện, cũng không giới hạn việc tự xây dựng APIs  Backend hoặc lựa chọn phương án sử dụng Localstorage phải có services giả lập APIs để mô phỏng hành động bất  đồng bộ. 

4. Yêu cầu
 - Tất cả dữ liệu từ phía người dùng phải được validate 
 - Phải có xác thực và phân quyền truy cập 
 - Typescript là 1 điểm cộng 
 - Unit test là 1 điểm cộng 
 - Home Page mô phỏng càng trực quan càng tốt 
 - Có thể thoải mái thêm các page tính năng khác 
 - UI thân thiện dễ dùng là 1 điểm cộng
