
<template>
    <div>
       <div class="news-holder" v-for="(newsContent, index) in news" :key="newsContent.id">
            <h1 class="text-danger">{{newsContent.name}}</h1>
            <h4 class="text-primary">{{newsContent.header}}</h4>
            <p>{{newsContent.body}}</p>
            <div class="mb-2 text-info">{{date}}</div>

           <div class="row">
               <div class="col-6">
                   <my-button :click-function="showDate" b-class="btn-danger btn-sm" b-text="show year"></my-button>
                   <my-button :click-function="tourEnded" b-class="btn-success btn-sm ml-3" b-text="end tour" :is-disabled="!isTourEnded"></my-button>
               </div>
               <div class="col-6">
                   <button type="button" class="btn btn-outline-primary btn-sm float-right" v-on:click="readNews(index + 1)">Read</button>
               </div>
           </div>

            <div style="border: 1px dashed;" class="mt-2"></div>
       </div>
    </div>
</template>


<script>
export default {
  name: "NewsHolder",

  props:{
      date:{
          type: String,
          required: false,
          default: 'today'
      }
  },

  data() {
      return {
          news: [
              {"name": "News 1", "header": "News 1 header", "body": "News 1 body info"},
              {"name": "News 2", "header": "News 2 header", "body": "News 2 body info"},
              {"name": "News 3", "header": "News 3 header", "body": "News 3 body info"}
          ],
      }
  },

  methods:{
      readNews(newsNum){
          this.$emit('read', newsNum);
      },

      showDate(){
    alert('Year is: ' + (new Date()).getFullYear())
}
  }
}

</script>