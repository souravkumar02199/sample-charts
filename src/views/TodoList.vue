<template>
    <v-container>
        <v-row class="text-center">
            <v-col cols="12">
                <!-- <h1>TodoList</h1> -->
                <ListaTareas />
                <PieChart />
                <TimeLineChart />
                <GradientDonut />
            </v-col>   
        </v-row> 
    </v-container>
</template>
<script>
import PieChart from '../components/PieChart.vue'
import ListaTareas from '../components/ListaTareas'
import TimeLineChart from '../components/TimeLineChart.vue'
import GradientDonut from '../components/GradientDonut.vue'
export default {
    components:{ ListaTareas,PieChart,TimeLineChart,GradientDonut},
    data() {
        return {}
    },
    
}
</script>