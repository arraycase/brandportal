<template>

    <div>
        <b-loading v-model="loading" ></b-loading>
        <!-- <div class="bottom-element">

            <div class="level ">
                <button class="level-item button">Heko</button>
            </div>
        </div> -->
        <div class="level is-mobile">
            <div class="level-left">
                <div class="level-item">
                    <div>

                        <p class="is-size-5 has-text-weight-semibold">Add New Products(s)</p>
                        <p>Upload at max 20 Images at a time to avoid upload delays</p>

                    </div>
                </div>
            </div>
            <div class="level-right">
                <div class="level-item">
                    <n-link to="/products" class="button">
                        <b-icon class="mr-2" icon="eye"></b-icon>
                        View</n-link>
                </div>
            </div>
        </div>
        <hr>
        <div class="">
            <b-field>
                <b-upload         @input="bulkUpload()"
 v-model="dropFiles" multiple
        drag-drop expanded>
                    <section class="section has-background-link-light has-text-link is-fullwidth">
                        <div class="content has-text-centered">
                            <p>
                                <b-icon icon="image-plus" size="is-large">
                                </b-icon>
                            </p>
                            <p>Drop your files here or click to upload</p>
                        </div>
                    </section>
                </b-upload>
            </b-field>
        </div>
        <section class="mt-2 my-0 px-0" v-show="data_files.length != 0">
            <article class="media notification has-background-info-light has-text-info mb-4">
                <div class="media-left">
                    <b-icon icon="alert-circle"></b-icon>
                </div>
                <div class="media-content">
                    <p class="">
                        Images marked in <span class="tag is-rounded is-danger has-text-weight-semibold">RED</span> exceed <span class="has-text-weight-semibold">1 MB</span>, may take more time to upload depending on your connection
                    </p>
                </div>
            </article>
            <div class="columns is-multiline">
                <div :key="index" class="column is-3" v-for="(img, index) in data_preview">
                    <div class="box box-dumb"  :class="{
                        'box has-background-danger-light':
                            data_files[index].files.size > 1000000,
                    }">
                        <figure class="image">
                            <img ref="pre_img" class="image-preview" v-bind:src="img" />
                        </figure>

                        <div class="my-3">

                            <p class="has-text-weight-bold ">
                                {{ data_files[index].files.name }}
                            </p>
                            <p class="has-text-weight-normal">
                                File size: {{ data_files[index].files.size | formatBytes }}
                            </p>
                        </div>
                        <button @click="deleteUpload(index)" class="mt-1 is-fullwidth button is-danger" :class="{
                        'is-light':
                            !(data_files[index].files.size > 1000000),
                    }"  >
                            <b-icon icon="close"></b-icon>
                            <span>Delete</span>
                        </button>
                    </div>
                </div>
            </div>
        </section>


    </div>
</template>
  
<script>
export default {
    name: 'HSN Add',
    layout: 'portal',
    data() {
        return {
            dropFiles: [],
            data_files: [],
            data_preview: [],
            loading: false,

        }
    },
    filters: {
    formatBytes(a, b) {
      if (0 == a) return "0 Bytes";
      var c = 1024,
        d = b || 2,
        e = ["Bytes", "KB", "MB", "GB", "TB", "PB", "EB", "ZB", "YB"],
        f = Math.floor(Math.log(a) / Math.log(c));
      return parseFloat((a / Math.pow(c, f)).toFixed(d)) + " " + e[f];
    },
  },

    methods: {
        bulkUpload() {
      let self = this;
      this.loading = true;
      if (this.dropFiles.length != 0) {
        this.dropFiles.forEach((item, index) => {
          let obj = {
            files: null,
          };
          if (this.data_files.length < index + 1) {
            obj.files = item;
            self.data_files.push(obj);

            let reader = new FileReader();

            reader.onload = function (event) {
              const imageUrl = event.target.result;
              self.data_preview.push(imageUrl);
            };
            reader.readAsDataURL(item);
          }
        });
      }
      this.loading = false;
    },

        formatSize(a, b) {
      if (0 == a) return "0 Bytes";
      var c = 1024,
        d = b || 2,
        e = ["Bytes", "KB", "MB", "GB", "TB", "PB", "EB", "ZB", "YB"],
        f = Math.floor(Math.log(a) / Math.log(c));
      return parseFloat((a / Math.pow(c, f)).toFixed(d));
    },
        deleteUpload(index) {
            this.dropFiles.splice(index, 1);
            this.data_files.splice(index, 1);
            this.data_preview.splice(index, 1);
        },
        deleteItem(index) {
            this.$delete(this.dropFiles, index);
            this.$delete(this.data, index);

        },
    }
}
</script>
  
