<template>
  <v-app>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-property-decorator';

@Options({})
export default class App extends Vue {

}
</script>

<style lang="scss">
@import './styles/main.scss';

</style>
