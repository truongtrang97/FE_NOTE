# cài đặt npm install @reduxjs/toolkit:
- có redux rùi thì npm add @reduxjs/toolkit
- các action creators được tạo tự động ở các reducerSlice
- reducer được khai báo luôn trong store .
- (xóa 2 file reducers và action ) 
+ các file trong redux toolkit :
- file store : store ni được khai báo bằng 1 api là configureStore nhận vào 1 object cos fil là reducer :
    - filter: lưu trữ lại những trạng thái mà ta filter (vd đoạn search là gì, by status ta đang chọn là gì , filter priority những giá trị nào)
    - todoList : lưu trữ lại tất cả những todo cần làm 
- các file Slice: dùng api có createSlice :
    - tạo ra reducer :có thể truy xuất reducer từ giá trị trả về của createSlide
    - dạng trả về 
    `{
        reducer,
        action 
    }
    `
    <!-- với những reducer sẽ tự động tạo ra những action creator tương ứng (action creators ni là 1 function trả về 1 action ) -->
    <!-- action ở đây vẫn có dạng :{
        type:
        payload: value
    } -->
