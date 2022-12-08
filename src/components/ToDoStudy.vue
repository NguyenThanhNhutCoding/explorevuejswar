<template>
  <ToDoItemStudy v-for="todo in todos" v-bind:key="todo" v-bind:TransferDataProps="todo"/>

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
            finish_yn: false
          },
          {
            id:2,
            title:'Work2',
            finish_yn: false
          }
        ])

        return{                     //---return này dùng để trả về giá trị
          todos
        }
      }
      
  }
</script>

<style>

</style>