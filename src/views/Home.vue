<template>
  <div class="controlled-components">
    <user-settings-form /> 
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import UserSettingsForm from '@/components/encapsulating-ext-behavior/Container.vue'; 

@Component({
  components: {
    UserSettingsForm,
  }
})
export default class Home extends Vue {}
</script>

<style lang="scss" scoped>
.controlled-components {
  display: flex;
  justify-content: center;
  width: 100%;
  margin-top: 50px;
}
</style>
