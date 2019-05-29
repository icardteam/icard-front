<template>
  <Table :columns="columns1" :data="tableData"></Table>
</template>

<script>
  import { getUserTableData } from "../../api/data";

  export default {
    name: "usersList",
    data(){
      return {
        tableData:[
        ],
        columns1: [
          {
            title: 'Name',
            key: 'name'
          },
          {
            title: 'Age',
            key: 'age'
          },
          {
            title: 'Phone',
            key: 'phone'
          }
        ],
      }
    },
    methods:{

    },
    mounted(){
      getUserTableData().then(res => {
        // console.log(res);
        this.tableData = res.data.data;
      }).catch(err => {
        console.log(err)
      })
    }
  }
</script>

<style scoped>

</style>
