<script>
import NavigationBar from '../components/NavigationBar.vue';
export default {
    setup() {
    },
    components: { NavigationBar }
}
</script>

<template>
    <NavigationBar/>
    <div id="content" class="d-flex align-items-center justify-content-center">
        <div class="container-fluid pt-5 ">
            <div class="pt-5 ">
                <div>
                    <div class="row">
                    <p class="title">Contact Me:</p>
                    </div>

                    <div class="row">
                        <h1 class="email">mark.manuel.business@gmail.com</h1>
                    </div>
                </div>
                
                
                
            </div>
        </div>
        
    </div>
</template>

<style scoped>
    #content{
        width:100vw;
        height: 100vh;
        background-color: var(--dark-green);
        display: block;
    }

    .email{
        color: var(--lighter-green);
        font-family: var(--mukta);
        font-size: 70px;
        word-wrap: break-word;
        animation-name: contact;
        animation-duration: 3s;
        animation-timing-function: ease;
    }

    .title{
        color: var(--lighter-green);
        font-family:var(--koulen);
        font-size: 100px;
        animation-name: contact;
        animation-duration: 2s;
        
        animation-timing-function: ease;
    }

    @media screen and (max-width: 400px) {
        .email{
            font-size: 50px;
        }
    }

    @keyframes contact {
        0%{
            opacity: 0;
        }
    }

</style>