## Kiến trúc của Redux và các khái niệm cần nắm 
- State management
    - Thực hiện theo 1 chiều : view-> Actions -> cập nhật lại state -> view nhận state và re-render lạino
- Immutability (Bất biến)
    - Không thay đổi giá trị object , array (không thao tác trực tiếp trên obj, arr)
    - Ta nên copy và thay đổi giá trị vào 1 arr , obj mới
## Kiến trúc của Redux:
### REDUCERS:
- Là 1 function : nó giúp cập nhật lại giá trị state ở store chung 
- Function ni nhận 2 đối số (state, action )
- Thực hiện action cần làm gì để cập nhật lại state tương ứng
- Một số quy tắc ràng buộc :
    - giá trị state mới tính toán luôn dựa trên state trước đó và action nếu có
    - Bắt buộc không bao giờ được thay đổi giá trị state hiện tại--> mà phải thực hiện immutability
    - Không được có bất kì đoạn code bất đồng bộ nào trong Reducers
                ` Không được sử dụng các function tính toán ngẫu nhiên`
                ` như Math.random(), hay Date.now()`
                ` các hành động request tới server , hoặc gọi API `
                - Tất cả các function theo các quy tắc trên gọi là PURE FUNCTION
`
const initValue ={value:0}
const rootReducer =(state=initValue, action)=>{
    Switch(action.type){
        case 'INCREMENT':
        return {
            ...state,
            value:state.value+1:
        }
        case 'todolist/increment':
        return{
            ...state,
            value: state.value + action.payload
        }
        <!-- đoạn ni không được thao tác trực tiếp
        state.value = state.value + 1
         -->
        default: 
        return state
    }

}
`
### ACTION
- action ni chỉ đơn giản là 1 object do ta quy định 
`
const INCREMENT =()=>{
    return{
    type: 'todolist/increment'
    payload: 10,
    }
}
`
<!-- Action creators -->
`const increamentCreators =(data)=>{
    return {
        type: 'todolist/increment123'
        payload: data,
    }
}
increamentCreators(10)
`
### DISPATCH:
- Là 1 function 
- cách duy nhất để cập nhật lại state trong store là sử dụng dispatch function   
- việc dispatch 1 hành động đơn giản hiểu bắn đi 1 action từ phía UI ( thực hiện 1 hành động trên trình duyệt )`
- dispatch nhận đối số là 1 action   
`dispatch(INCREMENT)`
`dispatch(increamentCreators(10))`
### cách kết nối giữa các thành phần của Redux
- 1 event click thực hiện UI ==> EVENT HANDLER được thực thi
- EVENT HANDLER thực hiện 1 function là DISPATCH 
- DISPATCH nhận vào 1 action và chuyển action vào Store vào Reducers--> cập nhật lại giá trị state
- UI nhận thông tin state trong store thay đổi và tiến hành re-render lại 

### Cơ chế tự động của Redux:
- Khi dispatch 1 action xong thì Reducer tự động lắng nghe action và cập nhật lại state
- Khi state trong store thay đổi thì các component có state tự động cập nhật và re-render lại trên UI
