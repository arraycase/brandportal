<template>

    <div>
        <div class="level is-mobile">
            <div class="level-left">
                <div class="level-item">
                    <div>

                        <p class="is-size-5 has-text-weight-semibold">Add a New Product Category</p>
                        <p class="is-size-6">Create categories to be used for assigning products</p>


                    </div>
                </div>
            </div>
            <div class="level-right">
                <div class="level-item">
                    <n-link to="/basic_master/product_category" class="button">
                        <b-icon class="mr-2" icon="eye"></b-icon>
                        View</n-link>
                </div>
            </div>
        </div>
        <hr>
        <div class="">

            <div class="columns is-centered is-mobile">
                <div class="column is-6-desktop">
                    <!-- <div class="notification box-dumb has-background-link-light"> -->

                    <b-field expanded label="Select Parent*">
                        <b-input placeholder="Select Parent"></b-input>
                    </b-field>
                    <hr class="my-5">
                    <b-field grouped>

                        <b-field expanded label=" Name">
                            <b-input placeholder="Product Category Name"></b-input>
                        </b-field>
                        <b-field expanded label="Short Name ">
                            <b-input class="is-uppercase" type="text-number" placeholder="Enter Short Name for SKU"></b-input>
                        </b-field>
                    </b-field>
                    <b-field grouped>

                        <b-field expanded label="HSN Code">
                            <b-input type="number" placeholder="Select HSN Code"></b-input>
                        </b-field>
                        <b-field expanded label="GST %">
                            <b-input type="number" placeholder="Enter %"></b-input>
                        </b-field>
                    </b-field>
                    <b-field grouped>

                        <b-field expanded label="UOM">
                            <b-input placeholder="Select UOM"></b-input>
                        </b-field>
                        <b-field expanded label="Multiple Qty">
                            <b-input type="number" placeholder="Enter Multiple"></b-input>
                        </b-field>
                    </b-field>
                    <b-field grouped>

                        <b-field expanded label="Add Tags">
                            <b-input icon="tag" placeholder="Add a Filter Tag"></b-input>
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
    name: 'Company',
    layout: 'portal',
    data() {
        return {
            banks: [],
            pageTab: 'basic',
        }
    },
    methods: {
        addBank() {
            let obj = {
                'bank_name': null,
                'bank_acc': null,
                'bank_ifsc': null,
                'bank_rex': null,
                'bank_swift': null,
                'bank_location': null,
            }
            this.banks.push(obj)
        }
    }
}
</script>
  
<style>
.border-top-green {
    border-top: 4px solid #dbdbdb;
}

.border-top-bank-green {
    border-top: 4px solid lightgreen;
}

.border-top-bank-blue {
    border-top: 4px solid lightblue;
}

.bank-pattern {}
</style>