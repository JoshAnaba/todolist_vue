<template>
    <div 
    class='todo-item'
    :class="{'is-complete':todo.completed}">
        <p >
            <input type="checkbox" @change='markComplete'>
            {{todo.title}}
            <button @click="$emit('del-todo' , todo.id)" class="del">X</button>
            </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ['todo'],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>


<style lang='scss' scoped>
p{  
    cursor: pointer;
    font-size: 20px;
    input[type="checkbox"]{
        cursor: pointer;
    }
}

.todo-item{
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.del{
    // background: #ff0000;
    background: rgb(88, 88, 88);
    color: #fff;
    padding: 12px 15px;
    font-weight: bold;
    cursor: pointer;
    float: right;
    border-radius: 5px;
    &:hover{
          background: rgb(132, 132, 132);
    }
}

.is-complete{
    text-decoration: line-through;
    background: #808080;
}
</style>