<template>
    <div id="app">
        <div>
            <vs-navbar :color="active" v-model="active">
                <template #left>
                    <vs-button flat icon :active="homeActive == 0" @click="homeClicked()">
                        <i class="fa fa-house"></i>
                    </vs-button>
                </template>
                <vs-navbar-item :to="'/feed'" :active="active == 'feed'" id="feed"> Feed </vs-navbar-item>
                <vs-navbar-item :to="'/profile'" :active="active == 'profile'" id="profile"> Profile </vs-navbar-item>
                <template #right>
                    <vs-button flat size="small" @click="$router.push('/login')">Login</vs-button>
                </template>
            </vs-navbar>
        </div>
        <div style="margin-top: 50px; height: 600px">
            <router-view />
        </div>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Vuesax from 'vuesax';

import 'vuesax/dist/vuesax.css'; //Vuesax styles
Vue.use(Vuesax, {});

@Component({
    components: {},
})
export default class Home extends Vue {
    private active = 'feed';
    private homeActive = 1;

    homeClicked(): void {
        this.homeActive = 0;
        this.$router.push('/');
    }
}
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

// #nav {
//     padding: 30px;

//     a {
//         font-weight: bold;
//         color: #2c3e50;

//         &.router-link-exact-active {
//             color: #42b983;
//         }
//     }
// }
</style>
