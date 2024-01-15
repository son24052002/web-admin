<template>
  
  <div>
    <v-row class="mt-3">
        <v-icon>mdi-home</v-icon>
        <h3 class="ml-2">Danh sách sản phẩm</h3>
        <v-spacer></v-spacer>
        <v-btn
            icon
            color="primary"
            size="small"
            @click="dialogAdd=true"
            >
            <v-icon>mdi-plus</v-icon>
        </v-btn>
    </v-row>

    <v-row class="mt-1">
        <v-col>
            <v-card>
                <v-table>
                    <thead>
                        <tr>
                            <th>STT</th>
                            <th>Product Name</th>
                            <th>Quantity</th>
                            <th>Price</th>
                            <th>Describle</th>
                            <th></th>
                        </tr>
                    </thead>
                </v-table>
            </v-card>
        </v-col>
    </v-row>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>