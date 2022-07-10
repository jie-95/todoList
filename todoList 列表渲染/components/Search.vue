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
            
            axios.get(`https://api.github.com/search/users?q=${this.keyWord}`).then(
                response => {
                    // console.log('请求成功',response.data.items);
                    this.$bus.$emit('updataListdata',response.data.items)

                },
                error => {
                    console.log('请求失败',error.message);

                }
            )
        }
    }
}
</script>

<style>

</style>