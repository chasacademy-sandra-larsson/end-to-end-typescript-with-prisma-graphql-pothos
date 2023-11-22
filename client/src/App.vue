<template>
  <div>
    <UserDetail v-for="user in result?.users" :key="user.name" :user="user" />
  </div>
</template>

<script  lang="ts">
import { defineComponent } from 'vue';
//import type { User } from '@/types';
import UserDetail from '@/components/UserDetail.vue';
import { useQuery } from '@vue/apollo-composable';
import { GetUsersDocument } from '@/graphql/generated';


export default defineComponent({
  name: 'App',
  components: {
    UserDetail
  },
  setup() {
    // const users: User[] = [
    //   { 
    //     name: 'Sandra',
    //     messages: [{
    //     body: 'all cred till prisma!'
    //   }, {
    //     body: 'testar lite'
    //   }],
    // }, 
    // {
    //   name: 'John',
    //   messages: [{
    //     body: 'all cred till prisma!'
    //   }, {
    //     body: 'testar lite'
    //   }],
    // }]
  // return {
  //   users
  // }
  const { result, loading, error } = useQuery(GetUsersDocument);
  
  return { result, loading, error };
}



})

</script>

<style scoped></style>
