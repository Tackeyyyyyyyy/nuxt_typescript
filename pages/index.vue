<template>
  <div>
    <h1>This is profile</h1>
    <TestComponent :profile="testProfile"/>
  </div>
</template>

<script lang="ts">
import {Component, Vue} from "vue-property-decorator";
import TestComponent from "~/components/TestComponent.vue";

@Component({
  components: {
    TestComponent,
  },
})

export default class IndexPage extends Vue {
  testProfileInfo = {
    name: "this is a title",
    sex: 1,
    age: 30,
  }

  get testProfile() {
    return this.testProfileInfo
  }
}
</script>
