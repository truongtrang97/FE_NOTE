## xử lý bất đồng bộ :
1. Brower API/web API 
- setTimeout, setInterval
- click, scroll...event
2. Promise : Các đối tượng JS để thực hiện các tác vụ bất đồng bộ 
3. Async_await
- cú pháp:
` const fnAsync= async ()=>{
    try{
     const fn1= await promise1
     <!-- code thực thi với fn1 -->
     const fn2= await promise2
     <!-- code thực thi với fn2 -->
     const fn3= await promise3
     <!-- code thực thi với fn3-->
    }catch(err){
     console.log(err)
    } }
    fnAsync()
`