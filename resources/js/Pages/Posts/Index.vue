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
                        <table class="table-auto">
                            <thead>
                                <tr>
                                    <th>SL</th>
                                    <th>Title</th>
                                    <th>Content</th>
                                    <th>Created At</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>1</td>
                                    <td>Malcolm Lockyer</td>
                                    <td>
                                        Lorem ipsum dolor sit amet consectetur
                                        adipisicing elit. Maxime mollitia,
                                        molestiae quas vel sint commodi
                                        repudiandae consequuntur voluptatum
                                        laborum numquam blanditiis harum
                                        quisquam eius sed odit fugiat iusto fuga
                                        praesentium optio, eaque rerum!
                                        Provident similique accusantium nemo
                                        autem.
                                    </td>
                                    <td>18-04-2022 11:02 pm</td>
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
    components: {
        AppLayout,
        Head,
    },
};
</script>
