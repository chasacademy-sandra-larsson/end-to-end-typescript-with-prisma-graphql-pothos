<template>
    <div>
        <h1>{{ user.name }}</h1>
        <MessageDetail v-for="message in user.messages" :key="message.body" :message="message" />
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import type{ PropType } from 'vue';
import type { User } from '@/types';
import MessageDetail  from '@/components/MessageDetail.vue';

    export default defineComponent({
        name: 'UserDetail',
        components: {
            MessageDetail
        },
        props: {
            user: {
                type: Object as PropType<User>,
                required: true
            }
        },
        setup() {
            return {

            }
        }
    })
</script>

<style scoped>

</style>