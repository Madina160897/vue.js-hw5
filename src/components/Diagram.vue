<script>
import fillСhart from './fillСhart.vue';
export default {

    components: {
        fillСhart
    },

    data() {
        return {
            diagrams: [],
            height: 0,
        }
    },
    methods: {
        diagramAll(data) {
            this.diagrams.push(data)
        }
    }
}

</script>

<template>
    <main>
        <fillСhart @add="diagramAll"/>

        <div class="fon">
            <div v-for="diagram in diagrams" :key="diagram.id" class="all">
                <p>{{ diagram.title }}</p>
                <div class="block-diag">
                    <div class="diagram" :style="{ height: diagram.percent + '%' }">{{ diagram.percent + '%' }}</div>
                </div>
            </div>
        </div>
    </main>
</template>

<style scoped>
main {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.diagram {
    width: 30px;
    background-color: rgb(63, 235, 235);
    position: absolute;
    bottom: 0;
}
.fon {
    display: flex;
    justify-content: left;
    border: 1px solid transparent;
}

.block-diag {
    height: 300px;
    width: 100%;
    position: relative;
    margin-left: 10px;
}

p{
    font-size: 16px;
    color: black;
}

.all{
    width: 40px;
    margin-left: 10px;
}

</style>