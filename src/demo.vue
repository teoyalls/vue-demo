<template>
    <section id="container">
        <div class="task-creat">
            <input type="text" v-model="task.content">
            <button @click="creatTask">添加任务</button>
        </div>
        <ul class="task-list">
            <li v-for="(item, index) in taskList">
                <input type="checkbox" @change="check(index)">
                {{ item.content }}
                <button class="btn" v-if="item.choose">删除2</button>
            </li>
        </ul>
    </section>
</template>

<script>
    export default {
        data() {
            return {
                task: {
                    content: '',
                    finish: false,
                    choose: false
                },
                taskList: []
            }
        },
        methods: {
            creatTask() {
                if(this.task.content != '') {
                    this.taskList.push(this.task);
                }
                this.task = {
                    content: '',
                    finish: false,
                }
            },
            check(index) {
                
            }
        }
    }
</script>

<style>
ul,
li {
    list-style: none;
}
</style>