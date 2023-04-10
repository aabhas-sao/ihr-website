<template>
  <div>
    <div>Observable Integration</div>
    <div ref="chartRef"></div>
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
    const inspect = Inspector.into(this.$refs.chartRef)
    this.notebookModule = runtime.module(notebook, name => {
      return name === 'chart' && inspect()
    })
  },
}
</script>
