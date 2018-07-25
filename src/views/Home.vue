<template>
  <div class="home">
    <div class="row py-3 px-5">
        <div class="col-2">
          <sidebar></sidebar>
        </div>
        <div class="col-10">
          <articles :articles="articles"></articles>
        </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Sidebar from '@/components/Sidebar.vue'
import Articles from '@/components/Articles.vue'
import axios from 'axios'

export default {
  name: 'home',
  components: {
    Sidebar,
    Articles
  },
  data: function () {
    return {
      articles: []
    }
  },
  methods: {
    getArticles: function () {
      const self = this
      axios({
        method: 'get',
        url: 'http://localhost:3000/articles'
      })
        .then(function (response) {
          self.articles = response.data
        })
    }
  },
  created () {
    this.getArticles()
    setTimeout(() => {
      // console.log(this.articles)
    }, 1000)
  }
}
</script>
