<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-12">
          <card>
            <template slot="header">
              <h4 class="card-title">All words in the site</h4>
              <p class="card-category">The choosen words which for Sefer's English lessons</p>
            </template>
            <div class="all-icons">
              <div class="row">
                <div class="font-icon-list col-lg-2 col-md-3 col-sm-4 col-6" v-for="word in words">
                  <div class="font-icon-detail">
                    <i class="nc-icon nc-air-baloon"></i>
                    <br/>
                    <router-link :to="{ name: 'SearchResult', params: { content: word.content  } }">{{ word.content }}</router-link>
                  </div>
                </div>
              </div>
            </div>
          </card>
        </div>

      </div>
    </div>
  </div>
</template>
<script>
import Card from 'src/components/Cards/Card.vue'
import StaticData from 'src/components/Data/StaticData.vue';
import SearchResult from './SearchResult.vue';

export default {
  components: {
    Card,
    StaticData,
    SearchResult
  },
  created() {
    this.words = StaticData.words;
  },
  data() {
    return {
      words: null,
      selectedWord: null
    }
  },
  methods: {
    
  }
}


</script>
<style>

</style>
