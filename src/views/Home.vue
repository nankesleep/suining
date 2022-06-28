<template>
  <Header /> 
  <Main />
  <Aside />
</template>

<script>
import Header from '@/components/home/Header';
import Aside from '@/components/home/Aside';
import Main from '@/components/home/Main'

export default {
  name: 'Home',
  components: {
    Header,
    Aside,
    Main
  }
}
</script>
