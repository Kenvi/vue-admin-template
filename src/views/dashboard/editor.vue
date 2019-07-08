<template>
  <div>
    <div id="content1" contentEditable="true" class="editDemo">jhh</div>
    <!-- <div class="mathquill-editable"></div> -->
  </div>
</template>
<script>
export default {
  data() {
    return {
      $: null, // jquery
      editor: null // editor实例
    }
  },
  async mounted() {
    const { editor, jquery } = await this.getEditor()
    // editor.disableAutoInline = true
    editor.inline('content1')
    this.editor = editor
    this.$ = jquery
    console.log(this.$.find('#content1'))
  },
  methods: {
    getEditor() {
      return new Promise(resolve => {
        const inter = setInterval(() => {
          if (window.JMEditor && window.JMEditor.ckEditor && window.$) {
            resolve({ editor: window.JMEditor.ckEditor, jquery: window.$ })
            clearInterval(inter)
          }
        }, 500)
      })
    }
  }
}
</script>

<style lang="scss">
  .cke{
    box-sizing: content-box;
  }
</style>
