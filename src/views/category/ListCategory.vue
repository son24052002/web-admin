<template>
  <div>
    <v-row class="mt-3">
        <v-icon>mdi-home</v-icon>
        <h3 class="ml-2">List Category</h3>
        <v-spacer></v-spacer>
        <v-btn
            icon
            color="primary"
            size="small"
            @click="showAddCategory = true"
            >
            <v-icon>mdi-plus</v-icon>
        </v-btn>
    </v-row>
    <v-row class="mt-1">
        <v-col>
            <v-card>
                <v-table>
                    <thead>
                        <tr >
                            <th>No</th>
                            <th>Category Id</th>
                            <th>Category Name</th>
                            <th>Actions</th>
                        </tr>
                        
                    </thead>
                    <tbody>
                        <tr v-for="(item, index) in Category " :key = "index">
                            <td>{{ index+1 }}</td>
                            <td>{{ item.CategoryId }}</td>
                            <td>{{ item.CategoryName  }}</td>
                            <td>
                                <v-btn
                                    color="blue"
                                    class="mr-3"
                                    icon
                                    size="x-small"
                                ><v-icon>mdi-pencil</v-icon>
                                </v-btn>

                                <v-btn
                                    color="red"
                                    class="mr-3"
                                    icon
                                    size="x-small"
                                ><v-icon>mdi-delete</v-icon>
                                </v-btn>
                            </td>
                        </tr>
                    </tbody>
                </v-table>
            </v-card>
        </v-col>
    </v-row>
    <add-category :visible="showAddCategory" @close="showAddCategory=false"/>
  </div>
</template>

<script>
import axios from 'axios'

import AddCategory from './AddCategory.vue'

export default {
    components: {AddCategory},
    name:'List-category',
    data(){
        return{
            Category:[],
            showAddCategory: false
        }
        
    },
    methods:{
        getCategory(){
            axios.get('https://65a48de652f07a8b4a3d7466.mockapi.io/Category')
            .then(response=>{
                this.Category = response.data;
                console.log(this.Category)
            }).catch(error =>{
                console.log(error)
            });
        },

        openAddCatDialog(){
            this.dialogVisible = true;
        },

    },
    created(){
        this.getCategory()
    }
}
</script>

<style>

</style>