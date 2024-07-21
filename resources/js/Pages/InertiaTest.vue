<script setup>
import { Head, Link } from '@inertiajs/vue3';
import { ref } from 'vue';
const newTitle = ref('');
const newContent = ref('');
</script>

<template>
    <div>
        Inertiaテストです。
    </div>
    <a href="/"> aタグ</a><br>
    <Link href="/"> Linkタグ</Link><br>
    <Link :href="route('inertia.index')"> 名前付きルートの確認です。</Link><br>
    <Link :href="route('inertia.show', { id: 1 })">ルートパラメータテスト</Link>

    <div class="mb-8">
    </div>

    <div>
        <input type="text" name="newTitle" v-model="newTitle">{{ newTitle }} <br>
        <input type="text" name="newContent" v-model="newContent">{{ newContent }} <br>

        <Link as="button" :href="route('inertia.store')" method="POST" :data="{
            title: newTitle,
            content: newContent
        }">DB保存テスト</Link>
    </div>


</template>
