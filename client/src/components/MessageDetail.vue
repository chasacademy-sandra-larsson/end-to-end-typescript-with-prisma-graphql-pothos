<template>
        <p>{{ message.body }}</p>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import type{ PropType } from 'vue';
import type { Message } from '@/types';

    export default defineComponent({
        name: 'MessageDetail',
        props: {
            message: {
                type: Object as PropType<Message>,
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