<template>
  <p class="todo-item is-finish" >
    <input type="checkbox" name="checkone" id="chk"/>
    {{TransferDataProps}}
    <button class="del-btn">Delete</button>
    <!-- <input type="button" name="delete" value="Delete" /> -->
  </p>
</template>

<script>
    export default {
        name: 'ToDoItemStudy',
        props:['TransferDataProps']       //...Dùng để truyền dữ liệu hay truyền Data giữa các components (giữa các trang .vue với nhau)
    }
</script>

<style>
.is-finish{
  text-decoration: line-through;         /*Ngạch ngang chuổi text */
}
  .todo-item{
    background: #f8ecf2;
    padding: 5px;                         /*padding: 5px(top:5px; right:5px; bottom:5px; left:5px*/
    margin: 0;                           /*margin:0 (Dùng để loại bỏ khoản trắng giữa hai dòng hay khoản cách giữa dòng mà bôi màu trắng)*/
    border-bottom: 1px #3399ff dotted;
  }
  .del-btn{
      background: #e6b3ff;
      color: #ff0000;
      border: none;                       /* Không hiển thị đường viền */
      cursor: pointer;                    /* Chuyển thành hình bàn tay khi đưa chuột vào để bấm */
      float: right;                       /* Chuyển phần tử sang phải */
  }
</style>