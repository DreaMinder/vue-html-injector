<template>
  <span>
    <template v-for="(chunk, i) in chunks">
      <span v-html="chunk" v-if="i % 2 === 0" />
      <slot v-else :name="chunk" />
    </template>
  </span>
</template>

<script>

export default {
  name: 'injector',
  props: ['content'],
  computed: {
    chunks(){
      return this.content.split('%%')
    }
  }
}

</script>
