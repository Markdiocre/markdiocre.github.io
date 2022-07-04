<script>
import { onMounted, ref } from '@vue/runtime-core';
import NavigationBar from '../components/NavigationBar.vue';
export default {
    setup() {

        let text = 'I am passionate with everything that deals with coding and design. Although I am just starting in the field, I appreciate collaborating with businesses and enthusiastic individuals that want to use beautiful design and engaging experiences to address challenges. I am for minimalism.'

        let text_html = ref('')
        let i = 0
        let speed = 20
        function typeWriter(){
            if (i < text.length) {
                text_html.value += text.charAt(i);
                i++;
                setTimeout(typeWriter, speed);
            }
        }

        onMounted(()=>{
            typeWriter()
        })

        return{
            text_html
        }
    },
    components: { NavigationBar }
}
</script>

<template>
    <NavigationBar/>
    <div id="content">
        <div class="container-fluid pt-5">
            <div class="p-5">
                <p class="title">Hey! I Am Mark.</p>

                <p class="sub-text">{{text_html}}</p>
            
            </div>
        </div>
        
    </div>
</template>

<style scoped>
    #content{
        width:100vw;
        height: 100vh;
        background-color: var(--dark-green);
        overflow: hidden;
    }

    .title{
        color: var(--lighter-green);
        font-family: var(--koulen);
        font-size: 128px;
        animation-name: title-animation;
        animation-duration: 2s;
        animation-timing-function: ease;
    }

    .sub-text{
        color: var(--light-green);
        font-family: var(--mukta);
        font-size: 64px;
    }

    @media screen and (max-width: 400px){
        .sub-text{
            font-size: 20px;
        }

        .title{
            font-size: 72px;
        }
    }

    @media screen and (min-width: 401px ) and ( max-width:560px){
        .sub-text{
            font-size: 24px;
        }

        .title{
            font-size: 80px;
        }
    }

    @media screen and (min-width: 561px ) and ( max-width:840px){
        .sub-text{
            font-size: 32px;
        }

        .title{
            font-size: 90px;
        }
    }

    @media screen and (min-width: 841px ) and ( max-width:1440px){
        .sub-text{
            font-size: 44px;
        }

        .title{
            font-size: 100px;
        }
    }

    @keyframes title-animation {
        0%{
            color: var(--dark-green);
            margin-bottom: 400px;
        }
    }

    @keyframes sub-text-animation {
        0%{
            color: var(--dark-green);
        }
    }

</style>