<template>
  <ToDoItemStudy 
       v-for="todo in todos"  
       v-bind:key="todo.id" 
       v-bind:TransferDataProps="todo"
       v-on:item-completed="markItemCompleted"/>
<!--Note: v-bind <=> : ex: v-bind:key <=> :key; v-bind:TransferDataProps <=> :TransferDataProps   -->
</template>

<script>
  import {ref} from 'vue'
  // import ToDoItemStudy from './components/ToDoItemStudy.vue' //...Lỗi do trang này cùng cấp với trang ToDoStudy đều trong thư mục components
  import ToDoItemStudy from './ToDoItemStudy.vue'  

  export default {
      name: 'ToDoStudy',
      components:{ToDoItemStudy},   //----component thư mục mục của hệ thống, phải đăng ký bởi vì thằng cha gọi thằng con, n
                                    //----Ngoài trường hợp trên thì còn trường hợp nào để đăng ký components nửa ko???

      setup(){                      //----phương thức hay hàm setup(){} Khi cần lấy dữ liệu để đưa lên <template></template>, nhưng hàm này trả về giá trị
        const todos = ref([
          {
            id:1,
            title:'Work 1',
            completed: false
          },
          {
            id:2,
            title:'Work 2',
            completed: false
          },
          {
            id:3,
            title:'Work 3',
            completed: false
          }
        ])
        const markItemCompleted = id =>{
            // console.log(id)

            //...toddos ko phải array có id ={1,2,3} nó là ref của array này 
            //ref giống như cái hộp bên trong chứa giá trị của todos này, todos này như cái hộp, chính là pointer, chuôi vào bên trong cái hộp
            //đó để lấy giá trị ra
            todos.value = todos.value.map(chktodo =>{
              if(chktodo.id === id) chktodo.completed = !chktodo.completed;
              return chktodo;
            }); //...map này biến đổi hàm array đó, lần lượt chạy qua từng phần tử của array đó

        }

        return{                     //---return này dùng để trả về giá trị
          todos,
          markItemCompleted
        }
      }
      
  }
</script>

<style>

</style>