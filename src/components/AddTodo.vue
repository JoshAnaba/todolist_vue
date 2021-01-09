<template>
    <div class='form-div'>
        <div class='state'>
            <button v-if='state==="default"' @click="changeState('edit')">Create a Todo</button>
            <button v-else @click="changeState('default')">Cancel</button>
        </div>
        <form v-if='state==="edit"' @submit.prevent = "addTodo">
            <input type="text" v-model="title" name='title' @keyup.enter='addTodo' placeholder="AddTodo...">
            <input type="submit" value="Add Todo" class="btn">
        </form>
    </div>
</template>

<script>
import {v4 as uuidv4} from 'uuid'
export default {
    name: "AddTodo",
    data(){
        return {
            title: '',
            state: 'default'
        }
    },
    methods: {
        addTodo(){
            const newTodo ={
                id: uuidv4(),
                title: this.title,
                completed: false
            }
            // send up to parent
            if(this.title!=''){
                this.$emit('add-todo', newTodo);
                this.title = '';
            }
        },

        changeState(newState){
            this.state = newState;
            this.title= ''
        }
    }
}
</script>

<style lang="scss" scoped>

.form-div{
    .state{
        display: flex;
        justify-content: flex-end;
        background-color: grey;
        border-bottom: 1px #ccc dotted;

        button{
            width: 145px;
            background: rgb(88, 88, 88);
            color: #fff;
            border-radius: 5px;
            height: 50px;
            cursor: pointer;
            &:hover{
                background: rgb(132, 132, 132);
            }
        }
    }
}
form{
    display: flex;
    height: 50px;

    input[type="text"]{
        flex: 10;
        padding: 5px;
    }

    input[type="submit"]{
        flex: 2;
        font-weight: bold;
        color: #fff;
        background: rgb(88, 88, 88);
        cursor: pointer;
        &:hover{
            background: rgb(132, 132, 132);
        }
    }
}


</style>