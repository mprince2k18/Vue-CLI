<template>
  <!-- form -->

  <div class="blog-app">

    <form>
    <div class="form-group">
      <label for="exampleInputEmail1">Add New Blog</label>
      <input type="text" v-model="blog.title" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Add New Blog">
    </div>
    <div class="form-group">
      <label for="exampleInputPassword1">Add Blog Content</label>
      <textarea class="form-control" v-model="blog.body"></textarea>
    </div>

    <div class="form-group">
      <label for="exampleInputPassword1">Blog Categories</label>
      <select class="form-control" v-model="blog.category">
        <option v-for="category in blog.categories" v-bind:key="category">{{ category }}</option>
      </select>

    </div>



    <button type="submit" @click.prevent="post" class="btn btn-primary">Submit</button>
  </form>
  <!-- <h1>{{ blog.title }}</h1>
  <h1>{{ blog.body }}</h1> -->


</div>











  <!-- form -->





</template>

<script type="text/javascript">
  export default {
    name: 'HelloPrince',
    data() {
      return {
          blog:{
            title: "",
            body: "",
            categories:['Music','Rock','Nu Metal'],
          }
      }
    },
    methods:{
      post:function(){
        const postData = { title: this.blog.title, body: this.blog.body };
        this.$http.post("https://laravel-6ae0a.firebaseio.com/post.json", postData).then(res => {
        // console.log(res.body);
        this.blog = res.body;
        // console.log(this.blog);
        });
      }
    },
  //   created() {
  //   this.$http.get("https://jsonplaceholder.typicode.com/posts/1").then(res => {
  //     this.blog = res.body;
  //   });
  // }
  }

  // export default {
  //   name:'recived',
  //   data(){
  //     return{
  //       blogs:[]
  //     }
  //   },
  //   created(){
  //     this.$http.get('https://jsonplaceholder.typicode.com/posts').then(res => {
  //     this.blogs = res.body;
  //     console.log(this.blogs);
  //   });
  //   }
  // }
</script>
