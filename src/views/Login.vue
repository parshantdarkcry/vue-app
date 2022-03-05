<template>
    <div class="login-page">
        <div v-if="displayState == 0" class="landing-state">
            <vs-button size="xl" circle @click="signInHandler()" style="margin-bottom: 10px"> Sign In </vs-button>
            <vs-button size="xl" circle @click="signUpHandler()"> Sign Up </vs-button>
        </div>
        <div v-else-if="displayState == 1" class="login-form">
            <div class="login-input">
                <vs-input class="login-input" label-placeholder="Email" v-model="email" />
                <vs-input class="login-input" label-placeholder="Password" v-model="password" />
            </div>
            <div>
                <vs-button class="login-cta" size="xl" circle @click="signInHandler()" style="margin-bottom: 10px">
                    Sign In
                </vs-button>
            </div>
        </div>
        <div v-else class="login-form">
            <div class="login-input">
                <vs-input class="login-input" label-placeholder="Email" v-model="email" />
                <vs-input class="login-input" label-placeholder="Password" v-model="password" />
            </div>
            <div>
                <vs-button class="login-cta" size="xl" circle @click="signInHandler()" style="margin-bottom: 10px">
                    Sign In
                </vs-button>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
    name: 'Login',
    components: {},
})
export default class Login extends Vue {
    private displayState = 0;
    private username = '';
    private fullname = '';
    private email = '';
    private password = '';
    private createpassword = '';
    private confirmPassword = '';

    signInHandler(): void {
        console.log('sign in');
        this.displayState = 1;
    }

    signUpHandler(): void {
        this.displayState = 2;
        console.log('sign up');
    }
}
</script>

<style scoped lang="scss">
.login-page {
    display: flex;
    justify-content: center;
    height: 100%;
    width: 100%;
    .landing-state {
        display: block;
        margin: auto 0px;
    }
    .login-form {
        margin: auto;
    }
    .login-input {
        margin: 10px;
    }
    .login-cta {
        margin-top: 40px;
        margin-left: 25px;
    }
}
</style>
