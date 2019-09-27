<template>
    <div>
        <p v-if="!user.email">No developer profile found for this requester.</p>
        <template v-else>
            <p><a :href="'mailto:' + user.email" target="_blank" >{{ user.email }}</a></p>
            <a v-if="user.github" :href="'https://github.com/' + user.github" target="_blank">
                <img src="../assets/github_octocat.png">
            </a>
            <a v-if="user.linkedin" :href="'https://www.linkedin.com/in/' + user.linkedin" target="_blank">
                <img  src="../assets/linkedin.png">
            </a>
        </template>
    </div>
</template>

<style scoped>
a {
    color: inherit;
    text-decoration: none;
}
</style>
<script>
export default {
    props: {
        user: {
            type: Object,
            required: true
        }
    }
}
</script>
