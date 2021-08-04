<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

import ClassicEditor from '@ckeditor/ckeditor5-editor-classic/src/classiceditor';

import EssentialsPlugin from '@ckeditor/ckeditor5-essentials/src/essentials';
import BoldPlugin from '@ckeditor/ckeditor5-basic-styles/src/bold';
import ItalicPlugin from '@ckeditor/ckeditor5-basic-styles/src/italic';
import LinkPlugin from '@ckeditor/ckeditor5-link/src/link';
import ParagraphPlugin from '@ckeditor/ckeditor5-paragraph/src/paragraph';
import Base64UploadAdapter from '@ckeditor/ckeditor5-upload/src/adapters/base64uploadadapter';

import Image from '@ckeditor/ckeditor5-image/src/image';
import ImageCaption from '@ckeditor/ckeditor5-image/src/imagecaption';
import ImageStyle from '@ckeditor/ckeditor5-image/src/imagestyle';
import ImageToolbar from '@ckeditor/ckeditor5-image/src/imagetoolbar';
import ImageUpload from '@ckeditor/ckeditor5-image/src/imageupload';
import ImageResizeEditing from '@ckeditor/ckeditor5-image/src/imageresize/imageresizeediting';
import ImageResizeHandles from '@ckeditor/ckeditor5-image/src/imageresize/imageresizehandles';

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      editor: ClassicEditor,
        editorData: '<p>Content of the editor.</p>',
        editorConfig: {
            // The configuration of the editor.
          plugins: [
                      EssentialsPlugin,
                      BoldPlugin,
                      ItalicPlugin,
                      LinkPlugin,
                      ParagraphPlugin,
                      Base64UploadAdapter,
                      Image,
                      ImageCaption,
                      ImageStyle,
                      ImageToolbar,
                      ImageUpload,
                      ImageResizeEditing,
                      ImageResizeHandles
                  ],

                  toolbar: {
                      items: [
                          'bold',
                          'italic',
                          'link',
                          'undo',
                          'redo',
                          'uploadImage'
                      ]
                  },
                image: {
                  toolbar: [ {
                      // Grouping the buttons for the icon-like image styling
                      // into one drop-down.
                      name: 'imageStyle:icons',
                      items: [
                          'imageStyle:alignLeft',
                          'imageStyle:alignRight',
                          'imageStyle:block'
                      ],
                      defaultItem: 'imageStyle:block'
                  },
                  ]
              }
        }
    }
  }
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
