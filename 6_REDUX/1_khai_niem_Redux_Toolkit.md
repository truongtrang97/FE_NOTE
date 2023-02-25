# Redux là 1 PATTERN (khuôn mẫu nên có khái niệm quy tắc cần tuân theo)
- Redux toolkit bản chất cũng là Redux
## Redux là gì:
- Là 1 thư viện JS để quản lý và cập nhật state(các dữ liệu hay các trạng thái ) của ứng dụng 
- Redux nó sử dụng các sự kiện , action 
- Nó hoạt động giống 1 kho lưu trữ tập trung cho các state được sử dụng ở các component, hoặc nhiều nơi trong ứng dụng 
- Đi kèm với nó là các quy tắc để ta đảm bảo là các state trong store chung này sẽ được cập nhật theo 1 cách mà ta có thể dự đoán được 
## Vì sao phải sử dụng redux (redux core)
- Quản lý global state
   - Các component tại mọi nơi trong ứng dụng có thể truy xuất và cập nhật
   - Giải quyết vấn đề của React khi muốn truyền dữ liêu vào các cấp con cháu
- Dễ dàng debug
    - khi có bug ta muốn biết các state này được cập nhật khi nào ở đâu và cách nó được cập nhật 
    - Hiểu ứng dụng của ta xử lý khi những thay đổi đó xảy ra 
    - Hướng code có thể dự đoán được và có thể test được 
- Xử lý caching (bộ nhớ đệm) dữ liệu từ phía server
## Vì sao cần sử dụng Redux toolkit
- Redux toolkit đơn giản là 1 thư viện JS 
- Nó bọc bên ngoài redux core
- Nó chứa các package và các function cần thiết khi sử dụng với redux, ta không cần cài đặt riêng lẻ 
- Nó giải quyết 3 vấn đề của redux core :
    - Việc cấu hình (config) Redux phức tạp 
    - Phaỉ  cài đặt thủ công nhiều packages để Redux có thể hoạt động hiệu quả  
    - Redux có rất nhiều boilerplate code ( đoạn code lặp đi lặp lại rất nhiều lần)
## Khi nào nên sử dụng redux 
- Hữu dụng trong các trường hợp :
    - Dự án có số lượng lớn state và các state này được sử dụng ở nhiều nơi
    - Các state được cập nhật thường xuyên 
    - Các logic code cập nhật state phức tạp 
    - Ứng dụng code lớn có nhiều người làm chung
    - Cần debug và muốn xem các state được cập nhật tại bất kì khoảng thời gian nào 
    -`không phải lúc nào cũng nên sử dụng redux`
