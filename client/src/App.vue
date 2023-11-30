<template>
  <div id="gjs"></div>
</template>

<script>
import grapejs from 'grapesjs'
import 'grapesjs/dist/css/grapes.min.css'
import 'grapesjs/dist/grapes.min.js'

export default {
  name: 'App',
  components: {},
  mounted() {
    grapejs.init({
      container: '#gjs',
      fromElement: true,
      height: '900px',
      width: 'auto',
      blockManager: {
        appendTo: '.myblocks',
        blocks: [
          {
            id: 'image',
            label: 'Image',
            media: `<svg style="width:24px;height:24px" viewBox="0 0 24 24">
            <path d="M8.5,13.5L11,16.5L14.5,12L19,18H5M21,19V5C21,3.89 20.1,3 19,3H5A2,2 0 0,0 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19Z" />
        </svg>`,
            // Use `image` component
            content: { type: 'image' },
            // The component `image` is activatable (shows the Asset Manager).
            // We want to activate it once dropped in the canvas.
            activate: true,
            // select: true, // Default with `activate: true`
          }
        ],
      },
      storageManager: false
    })
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
