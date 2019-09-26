<template>
    <div>
        <Loader v-if="loading"/>
        <Profile v-else :user="user"/>
    </div>
</template>

<script>
import Loader from '@/components/Loader.vue'
import Profile from '@/components/Profile.vue'
import client from '@/utils/zafclient.js'
import axios from 'axios'

export default {
    components: {
        Loader,
        Profile
    },
    data() {
        return {
            apiUrl: '',
            user: {},
            loading: true
        }
    },
    mounted() {
        client.get('ticket.requester.email').then((data) => {
            let email = data['ticket.requester.email'];
            this.getProfileData(email);
        });
    },
    methods: {
        getProfileData(email) {
            try {
                axios.get(apiUrl + email, {
                    validateStatus: false,
                    headers: {'Access-Control-Allow-Origin': '*'}
                }).then(response => {
                    this.user = {
                        ...response.data.data
                    }
                })
            } catch (err) {
                // eslint-disable-next-line no-console
                console.log(err);
            } finally {
                this.loading = false;
            }
        }
    }
}
</script>
