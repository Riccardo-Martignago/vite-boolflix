<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import { CalculationInterpolation } from 'sass';
export default {
    data() {
        return {
        }
    },
    components:{
      AppHeader,
      AppMain,
      AppFooter
    }
}
</script>

<template>
  <AppHeader />
  <AppMain />
  <AppFooter />
</template>

<style lang="scss">
@use './styles/partials/mixins' as *;
@use './styles/partials/variables' as *;
@use './styles/general.scss';
</style>
