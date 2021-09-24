<template>
  <ckeditor
    v-model="editorData"
    :editor="editor"
    :config="editorConfig"
  ></ckeditor>
</template>

<script>
import CKEditor from '@ckeditor/ckeditor5-vue2'
import ClassicEditor from '@ckeditor/ckeditor5-editor-classic/src/classiceditor'

import Bold from '@ckeditor/ckeditor5-basic-styles/src/bold'
import Italic from '@ckeditor/ckeditor5-basic-styles/src/italic.js'
import Underline from '@ckeditor/ckeditor5-basic-styles/src/underline'
import Strikethrough from '@ckeditor/ckeditor5-basic-styles/src/strikethrough'

// less Heading + Essentials plugin can't input the text
import Heading from '@ckeditor/ckeditor5-heading/src/heading'
import Essentials from '@ckeditor/ckeditor5-essentials/src/essentials'

import ImageUpload from '@ckeditor/ckeditor5-image/src/imageupload'
import ImageInsert from '@ckeditor/ckeditor5-image/src/imageinsert'
import AutoImage from '@ckeditor/ckeditor5-image/src/autoimage'
import Image from '@ckeditor/ckeditor5-image/src/image'
import ImageResizeEditing from '@ckeditor/ckeditor5-image/src/imageresize/imageresizeediting'
import ImageResizeHandles from '@ckeditor/ckeditor5-image/src/imageresize/imageresizehandles'
import Base64UploadAdapter from '@ckeditor/ckeditor5-upload/src/adapters/base64uploadadapter'

export default {
  name: 'VCKEditor',
  components: { ckeditor: CKEditor.component },
  props: {
    value: {
      type: String,
    },
  },
  computed: {
    editorData: {
      get() {
        return this.value
      },
      set(value) {
        this.$emit('input', value)
      },
    },
  },
  data() {
    return {
      editor: ClassicEditor,
      editorConfig: {
        plugins: [
          Bold,
          Italic,
          Underline,
          Strikethrough,
          Heading,
          Essentials,
          ImageUpload,
          ImageInsert,
          AutoImage,
          Image,
          ImageResizeEditing,
          ImageResizeHandles,
          Base64UploadAdapter,
        ],

        toolbar: {
          items: [
            'heading',
            '|',
            'bold',
            'italic',
            'underline',
            'strikethrough',
            '|',
            'insertImage',
          ],
        },
        language: 'zh',
      },
    }
  },
}
</script>
