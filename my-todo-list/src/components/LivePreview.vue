<template>
    <div class="live-preview">
        <h2>Live Preview</h2>
        <p>{{ newTodo }}</p>
    </div>
</template>

<script lang="ts">
export default {
    props: {
        newTodo: {
            type: String,
            required: true
        }
    }
};
</script>

<style scoped>
.live-preview {
    margin-top: 20px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    background-color: #f9f9f9;
}

h2 {
    margin: 0 0 10px;
    font-size: 1.2em;
    color: #333;
}

p {
    margin: 0;
    font-size: 1em;
    color: #555;
}
</style>
