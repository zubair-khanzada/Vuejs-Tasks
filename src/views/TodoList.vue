<template>
    <div class="todo-list-wrapper">
        <div class="todo-list">
            <h1>My To-Do List</h1>
            <form class="form-list" id="todo-form">
                <v-text-field v-model="todoTitle" id="todo-input" label="Add Title" color="primary" variant="outlined"></v-text-field>
                <v-btn color="primary" size="large" type="submit" @click="addTitleRow">
                    Add Task
                </v-btn>
            </form>
            <ul id="todo-list" class="mt-4">
                <li v-for="(item, index) in items" :key="index">
                    <span>
                        <v-checkbox color="primary"></v-checkbox>
                        {{item.name}}
                    </span>
                    <span>
                        <v-btn icon="mdi-pencil" color="primary" size="x-small"></v-btn>
                        <v-btn icon="mdi-delete" color="primary" size="x-small"></v-btn>
                    </span>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {
    name: "TodoList",
    data(){
        return {
            todoTitle: '',
            items: [
                {
                    name: "Learning Javascript"
                },
                {
                    name: "Learning Vuejs"
                }
            ]
        }
    },
    methods: {
        addTitleRow() {
            if (this.todoTitle.trim()) {
                this.items.push({ name: this.todoTitle });
                this.todoTitle = '';
            }
        }
    }
};

</script>

<style>

.todo-list-wrapper {
    display: flex;
    min-height: 100%;
    align-items: center;
    justify-content: center;
}
.todo-list {
    padding: 30px;
    margin: 0 auto;
    max-width: 600px;
    min-width: 600px;
    border-radius: 10px;
    box-shadow: 0 2px 5px 0 #cecece;
}
h1 {
    font-size: 26px;
    font-weight: 500;
    line-height: 30px;
    margin-bottom: 20px;
}
.form-list {
    gap: 20px;
    display: flex;
    align-items: center;
}
.form-list .v-input .v-input__details {
    display: none;
}
.form-list .v-btn {
    min-height: 56px;
}
ul li {
    display: flex;
    padding: 5px 10px;
    border-radius: 4px;
    margin-bottom: 5px;
    align-items: center;
    justify-content: space-between;
    box-shadow: 0 1px 3px 0 #cecece;
}
ul li span {
    gap: 10px;
    display: flex;
    align-items: center;
}
ul li .v-input__details {
    display: none;
}
ul li .v-checkbox {
    margin-left: -10px;
}
ul li .v-checkbox .v-selection-control {
    min-height: auto;
}

</style>