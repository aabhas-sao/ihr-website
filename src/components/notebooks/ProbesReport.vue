<template>
  <div>
    <h1>Observable Integration</h1>
    <div ref="ref"></div>
  </div>
</template>

<script>
import { Runtime, Inspector } from '@observablehq/runtime'
import notebook from '55feb27b515b0427'

export default {
  data() {
    return {
      notebookModule: null,
    }
  },
  mounted() {
    const runtime = new Runtime()
    const inspect = Inspector.into(this.$refs.ref)
    this.notebookModule = runtime.module(notebook, inspect)
  },
}
</script>
