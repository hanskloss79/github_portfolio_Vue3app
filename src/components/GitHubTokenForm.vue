<template>
    <form @submit.prevent="saveToken">
        <div>
            <label for="githubToken">Token Githuba</label>
            <br />
            <input id="githubToken" v-model="githubToken" />
        </div>
        <div>
            <input type="submit" value="Save token" />
            <button type="button" v-on:click="clearToken">Wyczyść token</button>
        </div>
    </form>
</template>

<script>
export default {
    name: "GitHubTokenForm",
    data() {
        return {
            githubToken: "",
        };
    },

    beforeMount() {
        //pobranie tokenu z lokalnego obiektu Storage gdzie dane są przechowywane pomiędzy sesjami 
        this.githubToken = localStorage.getItem("github-token");
    },

    methods: {
        saveToken() {
            localStorage.setItem("github-token", this.githubToken);
        },
        clearToken() {
            localStorage.clear();
        }
    },
};


</script>