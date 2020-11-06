<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add :addComment="addComment"/>    <!--组件间通信-->
      <List :comments="comments" :deleteComment="deleteComment"/>
    </div>
  </div>
</template>

<script>
  import Add from './components/Add'
  import List from './components/List'

  export default {
    data() {
      return {
        comments: [// 数据在哪个组件，更新数据的行为（方法）就应该定义在哪个组件
          {
            name: 'BOB',
            content: '还不错',
          },
          {
            name: 'Cat',
            content: 'VUE 还不错',
          }
        ]
      }
    },
    methods: {
      // 添加评论
      addComment (comment){
        //筛选前面的数据
        this.comments.unshift(comment)
      },
      //删除指定下标的评论
      deleteComment(index){
        this.comments.splice(index,1)
      }
    },
    components: {
      Add,
      List
    }
  }
</script>

<style scoped>

</style>
