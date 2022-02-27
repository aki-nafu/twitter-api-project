<template>
  <v-app id="inspire">
    <v-app-bar
      app
      shrink-on-scroll
      class="app-bar"
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Gathered TimeLine</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <v-row>
          <v-col
            v-for="user_id in user_ids"
            :key='user_id'
          >
            <v-card class="mx-auto">
              <v-card-title>
                <v-icon large left color="#26c6da">mdi-twitter</v-icon>
              </v-card-title>
              <v-flex xs12>
                <div>
                  <Timeline :id="user_id" sourceType="profile" :options="{ 'height': '700px'}"/>
                </div>
              </v-flex>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import { Timeline } from "vue-tweet-embed";
export default {
  components: {
    Timeline
  },
  data () {
    return {
      // ここにタイムラインを表示させたいアカウント名を追加する
      user_ids: ["mouchumaruta",'Gorgeous55555','dayukoume','tetsuyasaito111','dekkachan2003']
    };
  }
};
</script>

<style>
.app-bar{
  color: aqua;
}

</style>