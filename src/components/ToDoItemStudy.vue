<template>
  <p :class="['todo-item', TransferDataProps.completed ? 'is-completed' : '']">
    <input type="checkbox"  :checked="TransferDataProps.completed" 
            v-on:change="markItemCompleted" v-on:item-completed="markItemCompleted"/>
    {{TransferDataProps.title}}
    <button class="del-btn">Delete</button>
    <!-- <input type="button" name="delete" value="Delete" /> -->
  </p>
</template>

<script>   
    // import { ref, Ref } from 'vue';   //...First status...
                                         //..Create dataStoreSource of vue support ...
                                        //...No Need..

    export default {
        name: 'ToDoItemStudy',
        props:['TransferDataProps'],       //...Dùng để truyền dữ liệu hay truyền Data giữa các components (giữa các trang .vue với nhau)  
        setup(props, context){                           //...Always two parameters default(props, context)....
          const markItemCompleted = ()=>{
              // console.log(props.TransferDataProps)
              context.emit('item-completed', props.TransferDataProps.id)  //...phát đi tín hiệu từ component con lên component mẹ ('tùy chọn', 'bắt buộc')
          }
          return{
            markItemCompleted
          }

        }
    }
</script>

<style>
.is-completed{
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