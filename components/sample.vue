<template lang="html">
    <div class="sample">
        <h1>{{ title }}</h1>
        <h2>{{ subTitle }}</h2>
        ヤァ！{{ name }}だよ〜<br>
        {{ reversName }}
        <button type="button" name="button" @click="plus">
            クリック回数: {{ num }}
        </button>
        <div :class="['hide',{ seven: num === 7 }]">
            ７回目！！
        </div>
        <div class="red">
            <slot />
        </div>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: 'デフォルトタイトル'
        },
        subTitle: {
            type: String,
            default: '川口・所沢だよ'
        }
    },
    data() {
        return {
            name: 'シゲマリアッチ',
            num: 0,
        }
    },
    methods: {
        plus() {
            this.num++
        }
    },
    computed: {
        reversName () {
            return this.name.split('').reverse().join('')
        }
    }
}
</script>

<style lang="scss" scoped>
.hide {
    display: none;
    &.seven {
        display: block;
    }
}
.red {
    color: red;
    font-size: 58px;
}
.blue {
    color: blue;
}
</style>