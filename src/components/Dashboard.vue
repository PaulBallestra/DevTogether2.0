<template>
    <div id="container">

        <div style="margin: auto; width: 350px; height: 350px; background-color: white; position: relative;">

        <div id="compteur" style="position: absolute;">
            <ion-img src="assets/images/compteur_empty.png"></ion-img>
        </div>

        <div id="arrow" style="position: absolute;">
            <ion-img style="position: relative;" src="assets/images/compteur_arrow.png"></ion-img>
        </div>

        </div>
        <div id="container_compteur">

            <ion-button @click="decrement">
                <ion-img style="width: 25px;" src="assets/icon/minus.svg"></ion-img>
            </ion-button>

            <ion-label id="labelValue" style="margin: auto;">0</ion-label>

            <ion-button @click="increment">
                <ion-img style="width: 25px;" src="assets/icon/add.svg"></ion-img>
            </ion-button>

        </div>
    </div>
</template>

<script>

    import { IonImg, IonButton, IonLabel } from '@ionic/vue';
    import { defineComponent } from 'vue';


    let value = 0;

    export default defineComponent({
        name: 'Dashboard',
        components:{
            IonImg, IonButton, IonLabel
        },
        methods:{
            increment: function(e){

                e.preventDefault()

                const labelValue = document.getElementById('labelValue')
                const arrow = document.getElementById('arrow')

                if(value !== 200)
                    value++
                else
                    value = 200

                labelValue.innerHTML = value

                arrow.style.transform = 'rotate('+value*1.18+'deg)'

            },

            decrement: function(e){
                e.preventDefault()

                const labelValue = document.getElementById('labelValue')
                const arrow = document.getElementById('arrow')

                if(value !== 0)
                    value--
                else
                    value = 0

                labelValue.innerHTML = value
                arrow.style.transform = 'rotate('+value*1.18+'deg)'
            },
        }
    })

</script>

<style scope>

    #container{
        background-color: #1F1F1F; 
        padding: 36px; 
        border-radius: 5px; 
        margin: 64px auto 32px auto; 
        max-width: 520px; 
        display: flex; 
        flex-direction: column; 
        justify-content: center; 
        gap: 36px;
    }

    #container_compteur{
        margin: auto; 
        display: flex; 
        gap: 12px;
    }

</style>