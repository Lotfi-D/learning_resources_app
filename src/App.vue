<template>
<the-header title='Remember me'></the-header>
<the-resources></the-resources>
</template>

<script>
import TheHeader from './components/Header';
import TheResources from './components/TheResources';

export default {
    components:{
        TheHeader,
        TheResources
        },
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
