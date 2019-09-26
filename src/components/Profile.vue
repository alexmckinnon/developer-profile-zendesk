<template>
  <div>
    <span v-if="!user">No developer profile found for this requester.</span>
    <template v-else> 
        <span>{{ user.email }}</span>
        <img v-if="user.github" src="/github_octocat.png">
        <img v-if="user.linkedin" src="/linkedin.png">
    </template>
  </div>
</template>

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
