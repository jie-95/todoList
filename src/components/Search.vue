<template>
  <section class="jumbotron">
        <h3 class="jumbotron-heading">Search Github Users</h3>
        <div>
          <input
            type="text"
            placeholder="enter the name you search"
            v-model="keyword"
          />&nbsp;<button @click='SearchUsers'>Search</button>
        </div>
      </section>
</template>

<script>
import axios from 'axios'
export default {
    name:'Search',
    data(){
        return{
            keyword:''
        }
    },
    methods:{
        SearchUsers(){
            this.$bus.$emit('updataListData',{isFirst:false,isLoading:true,errmsg:'',users:[]})
            axios.get(`https://api.github.com/search/users?q=${this.keyWord}`).then(
                response => {
                    console.log('请求成功',response.data.items);
                  this.$bus.$emit('updataListData',{isLoading:false,errmsg:'',users:response.data.items})


                },
                error => {
                    console.log('请求失败',error.message);
                    this.$bus.$emit('updataListData',{isFirst:false,isLoading:true,errmsg:error.message,users:[]})

                }
            )
        }
    }
}
</script>

<style>

</style>