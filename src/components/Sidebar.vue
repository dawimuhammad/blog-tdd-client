<template>
    <div id="sidebar">
        <h5>Articles</h5>
        <ul class="nav flex-column">
            <li class="nav-item" v-for="(article, index) in articles" :key="index"> {{ article }} </li>
        </ul>
        <p>{{ articles }}</p>
    </div>
</template>

<script>
export default {
  props: [ 'articles' ]
}
</script>

<style>
#sidebar ul {
    list-style: none;
}

#sidebar li {
    padding-top: 7px;
    text-align: left;
}
</style>
