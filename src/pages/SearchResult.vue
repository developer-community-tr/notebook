<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-12" v-if="selectedWord">
          <card>
            <template slot="header">
              <h4 class="card-title">&nbsp;</h4>
              <p class="card-category">&nbsp;</p>
            </template>
            <div class="all-icons">
              <div class="row" style="justify-content: center;">
                <div class="font-icon-list col-lg-2 col-md-3 col-sm-4 col-6">
                  <div class="font-icon-detail">
                    <i class="nc-icon n c-air-baloon"></i>
                    <h3>{{ selectedWord.content }}</h3>
                  </div>
                </div>

              </div>
            </div>
            <div class="row">
              <div class="col-12">
                <card>
                  <h3>
                    <i class="nc-icon nc-puzzle-10" style="font-size: large;"></i>&nbsp;<small>Phrases :</small><br>
                    Make a story
                    <p>&nbsp;</p>
                  </h3>
                  <h3>
                    <i class="nc-icon nc-chat-round" style="font-size: large;"></i>&nbsp;<small>Saying :</small><br>
                    There is no story that never happened before in the world
                    <p>&nbsp;</p>
                  </h3>
                  <h3>
                    <i class="nc-icon nc-light-3" style="font-size: large;"></i>&nbsp;<small>Idioms :</small><br>
                    Bad choices makes good stories
                    <p>&nbsp;</p>
                  </h3>
                  <div class="footer">
                    <hr>
                    <div class="stats">
                      <i class="fa fa-spinner"></i> {{ selectedWord.metaData.level }}
                      <i class="fa fa-home"></i> {{ selectedWord.metaData.origin }}
                    </div>
                  </div>
                </card>
              </div>
            </div>
          </card>
        </div>
        <router-view :key="$route.path"></router-view>
      </div>
    </div>
  </div>
</template>
<script>
import Card from 'src/components/Cards/Card.vue';
import StaticData from 'src/components/Data/StaticData.vue'

export default {
  components: {
    Card,
    StaticData
  },

  data() {
    return {}
  },
  props: {
    content: {
      type: String,
      required: true
    }
  },
  created: function () {

  },
  computed: {
    selectedWord() {
      return StaticData.words.find(item => item.content === this.content);
    }

  }
}

</script>

<style>

</style>
