<script>
import twitData from "../twitData.json";
import NavBar from "./components/NavBar.vue";
import TwitTemplate from "./components/TwitTemplate.vue";
import TwitModal from './components/TwitModal.vue'
export default {
    name: "App",
    components: {
        NavBar,
        TwitTemplate,
        TwitModal, 
    },
    data() {
        return {
            twits: twitData,
            showModal: false,
        };
    },
    methods: {
        toggleModal() {
            this.showModal = !this.showModal;
            //console.log("Toggle Modal");
        },
        createNewTwit(newTwit){
            console.log('NewTwit function fired off with the argument...', newTwit); 
            this.twits.push(newTwit); 
            console.log(this.twits)
        }, 
    },
};
</script>

<template>
    <NavBar />
    <div class="twit-container">
        <TwitTemplate
            v-for="twit in twits"
            :key="twit"
            :text="twit.text"
            :author="twit.author"
            @text='newTwit'
        />
    </div>
    <footer>
        <button type="button" id="create-twit-button" @click="toggleModal"><i class="fas fa-bullhorn"></i></button>
        <div v-if="showModal">
            <TwitModal @close='toggleModal' @addTwit='createNewTwit' /> 
        </div>
    </footer>
</template>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

.twit-container {
    margin: 50px 10%;
    display: flex;
    flex-wrap: wrap;
}
</style>
