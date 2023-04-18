<template>

    <div>
        <div class="level is-mobile">
            <div class="level-left">
                <div class="level-item">
                    <div>

                        <p class="is-size-5 has-text-weight-semibold">Add GST %</p>


                    </div>
                </div>
            </div>
            <div class="level-right">
                <div class="level-item">
                    <n-link to="/basic_master/gst" class="button">
                        <b-icon class="mr-2" icon="eye"></b-icon>
                        View</n-link>
                </div>
            </div>
        </div>
        <hr>
        <div class="">

            <div class="columns is-centered is-mobile">
                <div class="column is-6-desktop">

                    <b-field expanded label="GST %">
                        <b-input  v-model="form.name" type="number" no-scroll placeholder="Enter GST%"></b-input>
                    </b-field>
                   
                    <div class="level is-mobile">
                        <div class="level-left">
                            <div class="level-item">
                                <button class="button is-text ">
                                    Clear
                                </button>
                            </div>
                        </div>
                        <div class="level-right">
                            <div class="level-item">
                                <button @click="() => { }" class="button is-black">
                                    <b-icon class="mr-2" icon="check"></b-icon>
                                    Save
                                </button>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>


    </div>
</template>
  
<script>
export default {
    name: 'GST Add',
    layout: 'portal',
    data() {
        return {
            form: {
                name:null,
            },
        }
    },
    methods: {
    }
}
</script>
  
