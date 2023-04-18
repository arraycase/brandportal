<template>

    <div>
        <div class="level is-mobile">
            <div class="level-left">
                <div class="level-item">
                    <div>

                        <p class="is-size-5 has-text-weight-semibold">Add New HSN Code</p>


                    </div>
                </div>
            </div>
            <div class="level-right">
                <div class="level-item">
                    <n-link to="/basic_master/hsn" class="button">
                        <b-icon class="mr-2" icon="eye"></b-icon>
                        View</n-link>
                </div>
            </div>
        </div>
        <hr>
        <div class="">

            <div class="columns is-centered is-mobile">
                <div class="column is-6-desktop">
                    <div class="notification has-text-info box-dumb has-background-info-light">
                        <div class="media">
                            <div class="media-left">
                                <b-icon icon="information"></b-icon>
                            </div>
                            <div class="media-content">
                                HSN Code and Description are <span class="is-underlined">unique</span>, so products can have same HSN code but diffirent descriptions.
                            </div>
                        </div>
                        </div>

                    <b-field expanded label="HSN Code">
                        <b-input  v-model="form.name" placeholder="Enter HSN Code - pref. 6 Digit"></b-input>
                    </b-field>
                    <b-field expanded label="HSN Description">
                        <b-input v-model="form.description" type="textarea" placeholder="HSN Code Description"></b-input>
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
    name: 'HSN Add',
    layout: 'portal',
    data() {
        return {
            form: {
                name:null,
                description:null,
            },
        }
    },
    methods: {
    }
}
</script>
  
