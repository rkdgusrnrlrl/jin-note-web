<template>
  <div>
    <textarea id="note-editor">{{text}}</textarea>
  </div>
</template>

<script>

export default {
  name: 'note-editor',
  data () {
    return {
      text: ''
    }
  },
  created () {

  },
  mounted () {
    const options = {
      element: document.getElementById('note-editor'),
      toolbar: ['bold', 'italic', 'heading', '|', 'code', 'quote', '|', 'unordered-list', 'ordered-list', '|', 'clean-block', '|', 'link', 'image', 'table', '|', 'preview'],
      placeholder: '여기에 글을 작성해주세요',
      spellChecker: false
    }
    let simplemde = new this.SimpleMDE(options)
    simplemde.value('')
  }
}
</script>

<style lang="scss">
.cm-quote-1 {
  color:gray;
}

.editor {
  > div {
    height: 100%;
    display: flex;
    flex-direction: column;

    .editor-toolbar {
      border-top-left-radius: 0;
      border-top-right-radius: 0;
    }

    .CodeMirror {
      flex:1;
    }
  }
}
</style>
