<template>
    <div class="post">
        <p>
           {{ content }}
        </p>
    </div>
</template>

<script>
    export default {
        // eslint-disable-next-line vue/multi-word-component-names
        name:'post',
        props:['content']
    }
</script>
<style>
    .post{
        background-color: darkblue;
        color: white;
        padding: 20px;
        margin-top: 20px;
        border-radius: 15px;
    }
    .post p{
        text-align: center;

    }
</style>