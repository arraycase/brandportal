<template>

    <div>
        <div class="level is-mobile">
            <div class="level-left">
                <div class="level-item">
                    <div>

                        <p class="is-size-5 has-text-weight-semibold">Add Currency</p>


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
                                Separate currency and pricing multiple factor can be used based on customer level. Allowing for different prices for diffrent segements of your customers 
                            </div>
                        </div>
                        </div>
                        <b-field grouped>

                            <b-field  label="Currency Name">
                                <b-field >

                                    <b-input icon="web"  v-model="form.name" placeholder="Enter Name"></b-input>
                                    
                                    <button class=" button has-text-weight-semibold">1</button>
                                </b-field>
                            </b-field>
                            <b-field expanded label="Exchange Rate">
                                <b-input  type="number" no-scroll v-model="form.exchange"  placeholder="Exchange Rate"></b-input>
                            </b-field>
                            <b-field expanded label="Multiple Factor">
                                <b-input type="number" no-scroll v-model="form.multiple"  placeholder="Enter Multiple"></b-input>
                            </b-field>
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
  
