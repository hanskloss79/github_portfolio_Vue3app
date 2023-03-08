<template>
    <div>
        <h1>Informacje o użytkowniku</h1>
        <ul>
            <li>
                <img id="avatar" :src="userData.avatar_url" />
            </li>
            <li>Nazwa użytkownika: {{ userData.login }}</li>
            <li>Obserwujący: {{ userData.followers }}</li>
            <li>Plan: {{ userData.pla && userData.plan.name }}</li>
        </ul>
    </div>
</template>

<script>
import { octokitMixin } from '@/mixins/octokitMixin';

export default{
    name: "githubUser",

    data(){
        return{
            userData: [],
        };
    },

    mixins: [octokitMixin],

    async mounted(){
        const octokit = this.createOctokitClient();
        const {data: userData} = await octokit.request("/user");
        this.userData = userData;
    },

    methods: {
        saveToken(){},
    },
};

</script>

<style scoped>
#avatar {
    width: 100px;
    height: 100px;
}
</style>