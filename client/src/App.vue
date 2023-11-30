<template>
  <div id="gjs"></div>
</template>

<script>
import grapejs from 'grapesjs'
// import plugin from 'grapesjs-preset-webpage';
import 'grapesjs/dist/css/grapes.min.css'
import 'grapesjs/dist/grapes.min.js'

export default {
  name: 'App',
  components: {},
  mounted() {
    let editor = grapejs.init({
      container: '#gjs',
      fromElement: true,
      height: '95vh',
      width: 'auto',
    })
    editor.Blocks.add('my-block-id', {
      label: 'My Block',
      content: {
        type: 'my-block-id',
        content: 'My Block',
      },
    })
    editor.Components.addType('my-block-id', {
      isComponent: el => el.tagName === 'MY-BLOCK-ID',
      model: {
        defaults: {
          traits: [
            {
              type: 'checkbox',
              name: 'repeat',
              label: 'Repeat',
            },
            {
              type: 'select',
              name: 'key',
              label: 'Key',
              options: [
                { id: '1', name: '1' },
                { id: '2', name: '2' },
                { id: '3', name: '3' },
              ],
            }
          ],
        },
      },
    })
  },
}
</script>

<style>
</style>
