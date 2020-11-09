<template>
<div id="body">
    <Header />
    <History />
    <ContentPage />
</div>
</template>

<script>
import Header from './Header'
import History from './History'
import ContentPage from './ContentPage'

export default {
    name: 'HelloWorld',
    data() {
        return {
            msg: 'Welcome to Your Vue.js App'
        }
    },
    components: {
        Header,
        History,
        ContentPage
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>

</style>
