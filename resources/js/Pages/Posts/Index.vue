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
                        <table class="min-w-full divide-y divide-gray-200 border">
                            <thead>
                                <tr>
                                    <th class="text-left px-6 py-4">SL</th>
                                    <th class="text-left px-6 py-4">Title</th>
                                    <th class="text-left px-6 py-4">Content</th>
                                    <th class="text-left px-6 py-4">Created At</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="(post, index) in posts" :key="post.id">
                                    <td class="px-6 py-5 whitespace-no-wrap">{{ index+1 }}</td>
                                    <td class="px-6 py-5 whitespace-no-wrap">{{ post.title }}</td>
                                    <td class="px-6 py-5 whitespace-no-wrap">
                                      {{ post.content }}
                                    </td>
                                    <td class="px-6 py-5 whitespace-no-wrap">{{ new Date(post.created_at).toLocaleString() }}</td>
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
import { Head } from "@inertiajs/inertia-vue3";
export default {
    props:{
         posts: Object
    },
    components: {
        AppLayout,
        Head,
    },
};
</script>
