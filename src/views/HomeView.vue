<template>
    <h1 class="title">
        This is Andrey and Eugene's page
    </h1>
    <div class="persons">
        <div v-for="({ pic, name }, index) in people" class="person">
            <h3>{{ name }}</h3>
            <img :src="pic"
                 :alt="name"
                 :key="index"
                 height="300"
            />
            <v-btn variant="flat" @click="sayHi(name)">Say Hi to {{ name }}</v-btn>
        </div>
    </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-property-decorator';
import andrey from '@/assets/faces/andrey.jpg';
import eugene from '@/assets/faces/eugene.jpg';


@Options({})
export default class HomeView extends Vue {
    public people = [
        {
            pic: andrey,
            name: 'Andrey',
        },
        {
            pic: eugene,
            name: 'Eugene',
        },
    ];

    public sayHi(name: string) {
        this.$toast.success(`Hi ${name}`!);
    }
}
</script>

<style lang="scss">
.title {
    text-align: center;
    margin: 20px;
}
.persons {
    display: flex;
    justify-content: space-around;
}
.person {
    & > * {
        display: block;
    }
}
</style>
