+ Truyền props vào component phải truyền dưới dạng destructuring {}
+ vd : Component_con ({props})
  + props ni chính là key của object được truyền vào khi được sử dụng component con ở component cha

+ truyền props sai có error: <cái ni là sai ngu cơ bản>
    ` Uncaught Error: Objects are not valid as a React child (found: object with keys {photoURL, displayName, text, createAt}). If you meant to render a collection of children, use an array instead.
    `

## một số event note:
- e là tham số của 1 số function thực hiện khi onChang đó là 1 event object (nên giá trị e.target.value)