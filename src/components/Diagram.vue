<script>
import AddDiagram from './AddDiagram.vue';
export default {
    components: {
        AddDiagram
    },
    data() {
        return {
            arr: [],
            height: 0,
        }
    },
    methods: {
        arrDiagram(data) {
            this.arr.push(data)

        }
    }
}

</script>

<template>
    <main>
        <AddDiagram @arr="arrDiagram" />
        <div class="block">

            <div v-for="item in arr" :key="item.id" class="mr-20">
                <div class="diagr">

                    <div class="diagramBlock" :style="{ height: item.percent + '%' }">{{ item.percent + "%" }}</div>
                </div>
                <p>{{ item.text }}</p>

            </div>
        </div>
    </main>
</template>

<style scoped>
main{
    display: flex;
    flex-direction: column;
    align-items: center;
}
.diagramBlock {
    width: 30px;
    background-color: rgb(24, 17, 238);
    position: absolute;
    bottom: 0;


}

.block {
    display: flex;
    justify-content: left;
    border: 1px solid transparent;
    margin-top: 50px;
    color: white;

}

.diagr {
    height: 300px;
    width: 100%;
    position: relative;
}

.mr-20 {
    margin-right: 20px;
}
</style>