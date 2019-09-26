<template>
  <div class="home">
    <Profile :email="email"/>
  </div>
</template>

<script>
import Profile from '@/components/Profile.vue'
import client from '@/utils/zafclient.js'

export default {
    components: {
        Profile
    },
    data() {
        return {
            email: ''
        }
    },
    mounted() {
        client.get('ticket.requester.email').then((data) => {
            this.email = data.ticket.requester.email;
        });
    }
}
</script>
