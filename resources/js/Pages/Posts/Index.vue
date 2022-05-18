<template lang="">
    <Head title="Post Lists" />
    <AppLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Post Lists
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <a :href="route('posts.create')" class="w-4 bg-sky-500 p-2 text-white rounded-md">Create New Post</a>
                        <table class="min-w-full divide-y divide-gray-200 border mt-4">
                            <thead>
                                <tr>
                                    <th class="text-left px-6 py-4 border">SL</th>
                                    <th class="text-left px-6 py-4 border">Title</th>
                                    <th class="text-left px-6 py-4 border">Content</th>
                                    <th class="text-left px-6 py-4 border">Created At</th>
                                    <th class="text-left px-6 py-4 border">Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="(post, index) in posts" :key="post.id">
                                    <td class="px-6 py-5 whitespace-no-wrap border">{{ index+1 }}</td>
                                    <td class="px-6 py-5 whitespace-no-wrap border">{{ post.title }}</td>
                                    <td class="px-6 py-5 whitespace-no-wrap border">
                                      {{ post.content }}
                                    </td>
                                    <td class="px-6 py-5 whitespace-no-wrap border">{{ post.created_at }}</td>
                                    <td class="px-6 py-5 whitespace-no-wrap border">
                                    <button type="button" @click.prevent="destroy(post.id)"
                                    class="px-4 py-1 mx-2 text-sm bg-red-600 text-white font-semibold rounded border"
                                >
                                    Delete
                                </button>
                                    </td>
                               </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
<script>
import AppLayout from "../../Layouts/Authenticated.vue";
import { Head, Link } from "@inertiajs/inertia-vue3";
import { Inertia } from '@inertiajs/inertia';
export default {
    props:{
         posts: Object
    },
    components: {
        AppLayout,
        Head,
        Link
    },

    setup(){
          const destroy = (id) => {
              if(confirm('Are You Sure?')){
                  Inertia.delete(route('posts.destroy', id))
              }
          }

          return {destroy}
    }
};
</script>
