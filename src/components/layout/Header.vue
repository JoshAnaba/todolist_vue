<template>
    <header class='header'>
        <h1>TodoList</h1>
         <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang='scss' scoped>

.header{
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px;
    border-radius: 10px 10px 0 0;

    a{
        color: #fff;
        padding-right: 5px;
        text-decoration: none;
    }
}
</style>