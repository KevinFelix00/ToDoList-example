<template>
    <div>
        <form>
        <input type="text" name="title" placeholder="Add Task...">
         <button class="btn" :style="{background:color}">{{ text }}</button>
        </form>
    </div>
</template>

<script>
export default {
    name:'AddTask',
    props: {
        text: String,
        color: String
    }
}
</script>