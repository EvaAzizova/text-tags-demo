<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />
        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>
      <v-spacer></v-spacer>
      <v-btn href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank" text>
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <router-view></router-view>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
  body {
    margin: 0;
    padding: 0;
    font-family: 'Roboto', sans-serif;
    background-color: #f6f6f6;
  }
</style>

<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title>Примеры использования компонента TextTags</v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <!-- Компонент на всю ширину экрана с выравниванием по левому краю -->
        <TextTags :tags="tags" alignment="left" full-width></TextTags>

        <!-- Компонент на всю ширину экрана с выравниванием по ширине -->
        <TextTags :tags="tags" alignment="width" full-width></TextTags>

        <!-- Компонент на 50% ширины экрана с выравниванием по левому краю -->
        <v-row>
          <v-col cols="6">
            <TextTags :tags="tags" alignment="left"></TextTags>
          </v-col>
          <!-- Компонент на 50% ширины экрана с выравниванием по ширине -->
          <v-col cols="6">
            <TextTags :tags="tags" alignment="width"></TextTags>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import TextTags from './components/TextTags.vue';

export default {
  name: 'App',
  components: {
    TextTags,
  },
  data() {
    return {
      tags: [
        { text: 'Тег1' },
        { text: 'Тег2', icon: 'mdi-star' },
        { text: 'Тег3' },
        { text: 'Тег4' },
        { text: 'Тег5' },
      ],
    };
  },
};
</script>

<style>
/* Добавьте необходимые стили здесь */
</style>
