<template>
  <v-dialog
    max-width="640px"
    v-model="showAddCatDialog"
  >
    <v-card>
        <v-card-title>
            <span>Add Category</span>
        </v-card-title>

        <v-card-text>
            <v-form>
                <v-container>
                    <v-row>
                        <v-col>
                            <v-text-field
                            label="Category Name">
                            </v-text-field>
                        </v-col>
                    </v-row>
                </v-container>
            </v-form>
        </v-card-text>
        <v-divider></v-divider> <!-- đường kẻ -->
        <v-card-actions>
            <v-spacer></v-spacer>
            
            <v-btn color="grey" flat @click="showAddCatDialog=false">Close</v-btn>
            <v-btn color="primary" flat @click ="addCategory">Save</v-btn>
        </v-card-actions>

    </v-card>
  </v-dialog>
</template>

<script>
export default {
    props: ['visible'],
    data(){
        return{
            data:{
                categoryName:''
            }
        }
    },
    computed:{
        showAddCatDialog:{
            get (){
                return this.visible
            },
            set (value){
                if(!value){
                    this.$emit('close')
                }
            }
        }
    }
};
</script>

<style>

</style>