<script>
import { onMounted, onUnmounted, ref } from '@vue/runtime-core'
export default {
    setup() {
        let descriptions = [
            'Fullstack Web Developer',
            'Aspiring UX/UI Designer',
            'Aspiring Indie Game Developer',
            'Aspiring Machine Learning Engineer'
        ]

        let count = ref(0)
        let desc = ref(descriptions[count.value])

        let inter =  setInterval(()=>{
            desc.value = descriptions[count.value]

            if(count.value >= descriptions.length -1){
                count.value = 0
            }else{
                count.value += 1
            }
        }, 2000)

        function open(e){
            if(e == 1){
                window.open('https://github.com/Markdiocre', '_blank').focus();
            }
        }

        onMounted(()=>{
            inter
        })

        onUnmounted(()=>{
            window.clearInterval(inter)
        })

        return{
            desc,
            open
        }
    },
}
</script>

<template>
    <div id="home" class="d-flex align-items-center justify-content-center">
        <div class="container-fluid">
            <div class="row text-center">
                <h1 class="name">Mark Thaddeus Manuel</h1>
                <p class="sub-title">mark.manuel.business@gmail.com</p>
            </div>
            <div class="row text-center">
                <h3 class="sub-title">{{desc}}</h3>
            </div>
            <div class="row text-center">
                <h3 class="icons pt-3">
                    <span class="me-4 icon" @click="open(1)">
                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
                            <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
                        </svg>
                    </span>
                </h3>
            </div>
            
        </div>
    </div>

</template>

<style scoped>
    
    #home{
        height: 100vh;
        width: 100%;
        background-color: #2F3E46;
    }

    .name{
        color: var(--lighter-green);
        font-size: 48px;
        font-family: var(--koulen);
        letter-spacing: 0.15em;
        animation-name: onLoad;
        animation-duration: 2s;
        animation-timing-function: ease;
    }

    .sub-title{
        color: var(--light-green);
        font-size: 24px;
        font-family: var(--mukta);
        letter-spacing: 0.15em;
        animation-name: onLoad;
        animation-duration: 2s;
        animation-timing-function: ease;
    }

    .icons{
        color: var(--light-green);
        font-size: 24px;
        font-family: var(--mukta);
        letter-spacing: 0.15em;
        animation-name: onLoad;
        animation-duration: 2s;
        animation-timing-function: ease;
    }

    .icon:hover{
        color: var(--lighter-green);
    }

    .sub-title:hover{
        color: var(--lighter-green);
    }

    @keyframes onLoad{
        0% {
            color: #2F3E46;
            margin-bottom: -40px;
            
        }

        50%{
            color: #2F3E46;
            margin-bottom: -40px;
        }
    }
</style>