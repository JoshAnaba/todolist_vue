<template>
    <div class='filter-section'>
        <div @click="$emit('show-all',todo)">All</div>
        <div @click="$emit('show-active', todo)">Active</div>
        <div @click="$emit('show-completed', todo)">Completed</div>
        <div @click="$emit('clear-completed', todo)">Clear Completed</div>
    </div>
</template>

<script>
export default {
    name: 'FilterSection'
}
</script>

<style lang='scss' scoped>

.filter-section{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 60px;
    padding: 5px;
    border-radius: 0 0 10px 10px;
    background:#fff;
    div{
        color: rgb(255, 255, 255);
        background: rgb(88, 88, 88);
        min-width: 20%;
        text-align: center;
        padding: 10PX;
        cursor: pointer;
        border-radius: 5px;
        box-shadow: 0 8px 6px -6px black;
         &:hover{
          background: rgb(132, 132, 132);
    }
    }
}
</style>
