## càì đặt debug:
1. `Redux DevTool`: giúp debug được ứng dụng Redux app trên Chorme ( xem được các trạng thái của kho chung được cài đặt ntn ở từng thời điểm ta mong muốn )
2. `React DeveloperTool`

# REDUX CORE:
1. cài đặt 2 pagekage: npm add redux react-redux
- note cài npm add redux@4.1.2 react-redux@7.2.6 dùng  với react@17
2. Tạo ra redux/store.js , reduce.js
3. todo list chia làm 2 phần: 
    - phần filfter
    - phần hiển thị danh sách các việc các làm hiện tại 
- Cần lưu dữ liệu vào kho chung  
    - Lưu tất cả các dữ liệu của trạng thái ta đăng nhập hiện tại -> để biết ta đang filter cái gì (dữ liệu filter)
    - Lưu state hiện tại ta đang có những việc cần làm ntn và mỗi việc cần làm có trạng thái ntn (dữ liệu todolist )
4. Cấu hình store xong và tích hợp vào dự án <=> (bọc App vào Provider để có thể dùng store chung cho tất cả các component con)
5.  Tạo ra action tương ứng với các hành động tương tác trên UI
    - Vd: Nhập vào thẻ input , chọn độ ưu tiên 
    - Nhấn vào nút add -> Đưa thông tin input và độ ưu tiên  vào làm danh sách cần làm hiển thị ở phía trên  trong danh sách todolist
    - Nhấn add -> cái ni là 1 action : addtodo
- action : dùng action creators
6. Viết 1 inventhandle chó sự kiện click lên button Add, onchange của seclect
    - dùng function dispatch từ useDispatch in react-redux
    - dispatch(action) <=>
    - dispatch ({nội dung ta cần nhập})
- Mỗi việc cần làm tương ứng với 1 id => nên ta install uuid để tự tạo ra id tự động
- lấy được value của onchangeinput
- lấy value của seclect priority 
- các giá trị value ni được đưa vào {} action bằng các state tương ứng với value
- ++ Khi dispatch 1 action thì bên phía reducer sẽ tự động được gọi 
- reducer (sửa action.payload để cập nhật dữ liệu input)
7. npm install --save redux-devtools-extension 
- cấu hình lại store 
- truyền tham số thứ 2 trong store là composedEnhancers=composeWithDevTools()
8. Tạo file seclector chứa từng loại dữ liệu của kho chung
9. Lấy dữ liệu trong kho chung:
10. Sử dụng useSeclector là 1 function dùng để lấy từng phần dữ liệu ở kho chung
- thêm npm add reselect ,
- <dùng toolkit thì không cần add cái ni đã có sẵn >
- vd : 1 selector này có dữ liệu dựa vào 1 selector khác 
- createSeletor(selector1,selector2,(dữ liệu selector1 trả về; dữ liệu selector2 trả về )=>{
    code xử lý dữ liệu 
})
- selector dùng để truy xuất các biến trong store chung
11. Làm việc với reducer nên chia nhỏ ra nhiều tính năng để ta dễ dàng quản lý và code dễ nhìn hơn