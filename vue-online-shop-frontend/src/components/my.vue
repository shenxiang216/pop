<template>
  <div>
    <div>
      <img src="../assets/zhao.jpg" alt="" id="zhaopian">
      <h3 v-on:click="getData">我的昵称：{{message}}</h3>
    </div>
  </div>
</template>

<style>
#zhaopian {
    width:200px;
    height:200px;
    border-radius: 50%;
}
</style>

<script>
export default {
    data(){
        return{
            
            message:"lalalalalalalalala"
        }
    },
    methods: {
        getData(){
            alert("服务器暂时无数据！")
            var api='http://www.phonegap100.com/appapi.php?a=getPortalCate'
            this.$http.get(api).then((response)=>{
                /* es6中this就指向当前上下文 ，非es6语法中需要提前设置that=this*/
                console.log(response)
                this.message=response.body.result
            },(err)=>{
                console.log(err)
            })
        }
    }
}
</script>
