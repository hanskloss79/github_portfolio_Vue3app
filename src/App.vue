<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Program Github</h1>
    <GitHubTokenForm />
    <githubUser />
    <userRepos />
  </div>
  
</template>

<script>
import GitHubTokenForm from './components/GitHubTokenForm.vue';
import userRepos from './components/Repos.vue';
import githubUser from './components/User.vue';



export default {
    name: "App",

    components: { 
      GitHubTokenForm, 
      githubUser, 
      userRepos }
};
</script>


