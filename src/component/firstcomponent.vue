<template>
    <div id="firstcomponent">
        <h1>I an a title.</h1>
        <a href="">written by {{ author }}</a>
    </div>
</template>

<script>
export default {
    data() {
        return {
            author: "Frank"
        }
    }
}
</script>
