<script>
import { ref } from '@vue/reactivity'
export default {
    setup() {
        
        let isActive = ref(false)

        function triggerMenu(){
            isActive.value = !isActive.value
        }

        return{
            isActive,
            triggerMenu
        }
    },
}
</script>

<template>
    <nav class="nav navbar fixed-top">
        <div class="container-fluid px-4">
            <router-link class="logo navbar-brand" :to="{name:'home'}">MTM</router-link>
            <div>
                <router-link :to="{name: 'about'}" class="pe-3 link">About</router-link>
                <router-link :to="{name: 'contact'}" >Contact</router-link>
            </div>
        </div>
    </nav>

</template>

<style scoped>
    .nav{
        background-color: var(--dark-green);
    }

    .logo{
        color: var(--lighter-green);
        font-family: var(--koulen);
        font-size: 2rem;
    }

    .text{
        color: var(--lighter-green);
        font-family: var(--mukta);
        font-size: 2rem;
    }

    #content{
        display: block;
        width: 100vw;
        height: 100vh;
        background-color: var(--lighter-green);
        position:fixed;
        bottom:0;
        right:0;
    }

    a{
        color: var(--lighter-green);
        font-family: var(--mukta);
        font-size: 2rem;
        text-decoration: none;
    }

    a:hover,
    a.router-link-active{
        color: var(--lighter-green);
        text-decoration: underline;
    }

</style>