<template>
    <div id="contriner">
        <ul class="tab-t">
            <li v-for="(tab, index) in tabs.tab" @click="handle(index)" :class="{cur: index == tabs.active}">
                {{ tab.title }}
            </li>
        </ul>
        <ul class="tab-c">
            <li v-for="(tab, index) in tabs.tab" :key="index" v-if="index == tabs.active">
                {{tab.content }}
            </li>
        </ul>
    </div>
</template>

<script>
    let tabDate = {
        active: 0,
        tab: [{
            title: '社会热点',
            content: '社会热点文字社会热点文字社会热点文字',
        },
        {
            title: '财经新闻',
            content: '财经新闻文字财经新闻文字财经新闻文字',
        },
        {
            title: '体育新闻',
            content: '体育新闻文字体育新闻文字体育新闻文字',
        }]
    };
    export default {
        data() {
            return {
                tabs: tabDate
            }
        },
        methods: {
            handle: (index) => {
                tabDate.active = index;
            }
        }
    }
</script>