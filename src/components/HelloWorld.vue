<template>
  <div class="hello">
    <div id="editor"></div>
  </div>
</template>

<script>
import FroalaEditor from 'froala-editor'
// Load a plugin.
import 'froala-editor/js/plugins/align.min.js'
import 'froala-editor/js/plugins/colors.min.js'
import 'froala-editor/js/plugins/draggable.min.js'
import 'froala-editor/js/plugins/image.min.js'
// Import Froala Editor css files.
import 'froala-editor/css/froala_editor.pkgd.min.css';
import 'froala-editor/css/plugins/draggable.min.css';
import 'froala-editor/css/plugins/image.min.css';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      editor:null
    }
  },
  mounted() {
    const config = {
      dragInline: false,
      pluginsEnabled: ['image', 'draggable']
    }
    this.editor = new FroalaEditor("#editor",config)
  },
  beforeDestroy() {
    this.editor.destroy()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
