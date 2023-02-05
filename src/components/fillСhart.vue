<script>
export default {
    data() {
        return {
            diagrams: [],
            title: "",
            percent: ""
        };
    },
    methods: {
        add() {
            this.$emit('add', {
                title: this.title,
                percent: this.percent
            })
            this.title = ''
            this.percent = ''
        }
    },

}

</script>

<template>
    <form class="Post" @submit.prevent>
        <input :value="title" @input="title = $event.target.value" type="text" placeholder="title">
        <input :value="percent" @input="percent = $event.target.value" type="number" placeholder="percent">
        <button class="btn" @click="add">Создать</button>
    </form>
</template>

<style>
.Post {
    display: flex;
    flex-direction: column;
    width: 400px;
    margin: 5% auto;
    border: 2px solid #2dcdd3;
    background-color: #f4f7f7;
    border-radius: 20px;
    padding: 5%;
    font-size: 16px;
}

input {
    margin-bottom: 20px;
    padding: 10px;
    font-size: 16px;
    border: 2px solid #5c9ea1;
    background-color: #ffffff9c;
    border-radius: 15px;
}

.btn {
    align-self: flex-end;
    font-size: 16px;
    padding: 10px;
    border-radius: 10px;
    background-color: rgb(216, 216, 216);
    border: 1px solid transparent;
    margin: 1%;
}
</style>