<template>
  <div>
    <div>Name: {{ profileName }} </div>
    <div>Sex: {{ profileSex }} </div>
    <div>Age: {{ profileAge }}  </div>
  </div>
</template>

<script lang="ts">
import {Vue, Component, Prop} from 'vue-property-decorator'

interface Profile {
  name: string
  sex: bigint
  age: bigint
}

@Component
export default class TestComponent extends Vue {
  @Prop({type: Object, required: true}) readonly profile!: Profile

  message: string = 'This is a message'

  get profileName(): string {
    return `${this.profile.name} `
  }

  get profileAge(): bigint {
    return this.profile.age
  }

  get profileSex(): string {
    if (this.profile.sex) {
      return "men"
    }
    return "women"
  }
}
</script>
