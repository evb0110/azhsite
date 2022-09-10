<template>
    <h1 class="title">
        This is Andrey and Zhenya's page

    </h1>
    <div class="faces">
        <img
            v-for="(src, i) in faces"
            :src="src"
            :alt="src"
            :key="i"
            class="my-3"
            height="200"
        />
    </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-property-decorator';
import zhenya from '@/assets/zhenya.jpg';
import andrey from '@/assets/andrey.jpg';


@Options({})
export default class HomeView extends Vue {
    public zhenya = zhenya;
    public andrey = andrey;
    public faces = [this.andrey, this.zhenya];
}
</script>

<style lang="scss">
.title {
    text-align: center;
}
.faces {
    display: flex;
    justify-content: space-around;
}
</style>
