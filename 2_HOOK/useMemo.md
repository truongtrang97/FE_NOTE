## Mounted/unmounted: (lắp vào và tháo ra )
- Mounted : thời điểm đưa component vào react element dom
- unmounted : thời điểm gỡ nó ra khỏi react element dom


## 
- hook 
- HOC -Higher order component (component bậc cao ) ==> memo 
- Render props 

## memo : giúp ghi nhớ lại các props của component , để nó quyết định có render lại component đó hay không , để tối ưu về hiệu năng 
- memo nó giúp xử lý component , giúp tránh re-render lại trong những tình huống không cần thiết 
- vd : khi dùng component con trong component cha thì thành phần trong component cha render làm cho component con cũng bị re-render lại

+  `cách dùng `:
- component con: memo(component con) --> chỉ render 1 lần, khi component cha render lại nó cũng vẫn không render lại, nếu props nó không đổi.
+ cách hoạt động memo :
- nó check các props của component đó sau mỗi lần component có bị thay đổi hay không, nếu ít nhất 1 props thay đổi thì nó sẽ re-render lại, còn không thì sẽ không render
- nó dùng toán tử '===' để so sánh

+ `note : Khi component cha chứa nhiều component con và độ phức tạp về UI nó lớn thì nên sử dụng memo cho tất cả component con để tránh re-render không cần thiết`
+ Trong 1 số tính năng đơn giản , mỗi khi state được update lại luôn dẫn tới component con re-render lại , thì không cần dùng memo

# USEMEMO : 
- nó giúp tránh thực hiện lại 1 logic nào đó không cần thiết
- cách dùng:
+ th1: 
`
const total =useMemo(()=>{
    <code logic>
},[])
--> chỉ chạy đoạn code logic ni 1 lần duy nhất `k render lại`
`
+ th2: 
`
const total =useMemo(()=>{
    <code logic>
},[dep])
--> nếu giá trị` dep thay đổi` thì code logic mới chạy và `re-render lại`, còn dep không thay đổi thì không rendẻ
`


