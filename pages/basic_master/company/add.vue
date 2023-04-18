<template>

    <div>
        <div class="level is-mobile">
            <div class="level-left">
                <div class="level-item">
                    <div>

                        <p class="is-size-5 has-text-weight-semibold">Add a New Company</p>
                        <p class="is-size-6">Create your company with Bank & Tax Details. This will be used in your
                            invoicing.</p>

                    </div>
                </div>
            </div>
            <div class="level-right">
                <div class="level-item">
                    <n-link to="/basic_master/company" class="button">
                        <b-icon class="mr-2" icon="eye"></b-icon>
                        View</n-link>
                </div>
            </div>
        </div>
        <hr>
        <div class="">

            <div class="columns is-centered is-mobile">
                <div class="column is-6-desktop">
                    <b-tabs v-model="pageTab" expanded>
                        <b-tab-item value="basic">
                            <template #header>
                                <span class="has-text-weight-medium">
                                    <span class="mr-1">

                                        1.
                                    </span>
                                    <span>
                                        Company Details
                                    </span>
                                </span>
                            </template>
                            <div>

                                <b-field label="Company Name">
                                    <b-input placeholder="Enter Company Name"></b-input>
                                </b-field>
                                <b-field label="Company Address">
                                    <b-input type="textarea" placeholder="Enter Company Name"></b-input>
                                </b-field>
                                <b-field label="GSTIN">
                                    <b-input placeholder="Enter GST Number"></b-input>
                                </b-field>
                                <b-field grouped>

                                    <b-field expanded label="City">
                                        <b-input placeholder="Enter City"></b-input>
                                    </b-field>
                                    <b-field expanded label="State">
                                        <b-input placeholder="Enter City"></b-input>
                                    </b-field>
                                    <b-field expanded label="Country">
                                        <b-input placeholder="Enter City"></b-input>
                                    </b-field>
                                </b-field>
                                <b-field label="PAN">
                                    <b-input placeholder="Enter PAN"></b-input>
                                </b-field>

                                <div class="level is-mobile">
                                    <div class="level-left">
                                        <div class="level-item">
                                            <button class="button is-text">Clear</button>
                                        </div>
                                    </div>
                                    <div class="level-right">
                                        <div class="level-item">
                                            <div class="level-item">
                                                <button @click="() => { pageTab = 'bank' }" class="button is-link">Next
                                                    <b-icon class="ml-2" icon="chevron-right"></b-icon></button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </b-tab-item>
                        <b-tab-item value="bank">
                            <template #header>
                                <span class="has-text-weight-medium">
                                    <span class="mr-1">

                                        2.
                                    </span>
                                    <span>

                                        Bank Details
                                    </span>
                                </span>
                            </template>
                            <div>
                                <b-collapse class="box box-dumb border-top-bank-green" animation="slide">
                                    <template #trigger="props">
                                        <div>

                                            <div class="level">
                                                <div class="level-left">
                                                    <div class="level-item">
                                                        <div>

                                                            <p class="has-text-weight-medium has-text-weight-semibold">
                                                                Primary Bank
                                                            </p>
                                                            <p class="has-text-weight-medium">
                                                                For Domestic Invoicing
                                                            </p>
                                                        </div>
                                                    </div>
                                                </div>
                                                <div class="level-right">
                                                    <div class="level-item">
                                                        <div v-if="!props.open">
                                                            <button class="button is-light">

                                                                <span class="">Show</span>
                                                                <b-icon icon="chevron-down"></b-icon>
                                                            </button>
                                                        </div>
                                                        <div v-else>
                                                            <button class="button is-light">

                                                                <span class="mr-2">Collapse</span>
                                                                <b-icon icon="chevron-up"></b-icon>
                                                            </button>
                                                        </div>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </template>
                                    <div>
                                        <hr>

                                        <b-field label="Bank Name">
                                            <b-input placeholder="Enter Bank Name"></b-input>
                                        </b-field>
                                        <b-field label="Bank Location">
                                            <b-input placeholder="Enter Bank Location"></b-input>
                                        </b-field>
                                        <b-field label="Account No.">
                                            <b-input placeholder="Enter Bank Account"></b-input>
                                        </b-field>
                                        <b-field label="Bank IFSC">
                                            <b-input placeholder="Enter Bank IFSC"></b-input>
                                        </b-field>
                                        <!-- <b-field label="">
                                            <b-input placeholder="Enter Bank IFSC"></b-input>
                                        </b-field> -->
                                        <div class="level">
                                            <div class="level-left">
                                                <button class="button is-light">
                                                    Clear</button>

                                            </div>

                                        </div>

                                    </div>

                                </b-collapse>
                                <b-collapse class="box box-dumb border-top-bank-blue" animation="slide">
                                    <template #trigger="props">
                                        <div>

                                            <div class="level">
                                                <div class="level-left">
                                                    <div class="level-item">
                                                        <div>

                                                            <p class="has-text-weight-medium has-text-weight-semibold">
                                                                Secondary Bank
                                                            </p>
                                                            <p class="has-text-weight-medium">
                                                                For International Invoicing
                                                            </p>
                                                        </div>
                                                    </div>
                                                </div>
                                                <div class="level-right">
                                                    <div class="level-item">
                                                        <div v-if="!props.open">
                                                            <button class="button is-light">

                                                                <span class="">Show</span>
                                                                <b-icon icon="chevron-down"></b-icon>
                                                            </button>
                                                        </div>
                                                        <div v-else>
                                                            <button class="button is-light">

                                                                <span class="mr-2">Collapse</span>
                                                                <b-icon icon="chevron-up"></b-icon>
                                                            </button>
                                                        </div>
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </template>
                                    <div>
                                        <hr>

                                        <b-field label="Bank Name">
                                            <b-input placeholder="Enter Bank Name"></b-input>
                                        </b-field>
                                        <b-field label="Bank Location">
                                            <b-input placeholder="Enter Bank Location"></b-input>
                                        </b-field>
                                        <b-field label="Account No.">
                                            <b-input placeholder="Enter Bank Account"></b-input>
                                        </b-field>
                                        <b-field label="Bank IFSC">
                                            <b-input placeholder="Enter Bank IFSC"></b-input>
                                        </b-field>
                                        <!-- <b-field label="">
                                            <b-input placeholder="Enter Bank IFSC"></b-input>
                                        </b-field> -->
                                        <div class="level">
                                            <div class="level-left">
                                                <button class="button is-light">
                                                    Clear</button>

                                            </div>

                                        </div>

                                    </div>

                                </b-collapse>


                                <div class="level is-mobile">
                                    <div class="level-left">
                                        <div class="level-item">
                                            <button @click="() => { pageTab = 'basic' }" class="button ">
                                                <b-icon class="mr-2" icon="chevron-left"></b-icon>
                                                Previous
                                            </button>
                                        </div>
                                    </div>
                                    <div class="level-right">
                                        <div class="level-item">
                                            <button @click="() => { pageTab = 'brand' }" class="button is-link">Next
                                                <b-icon class="ml-2" icon="chevron-right"></b-icon></button>
                                        </div>
                                    </div>
                                </div>
                            </div>

                        </b-tab-item>
                        <b-tab-item value="brand">
                            <template #header>
                                <span class="has-text-weight-medium">
                                    <span class="mr-1">

                                        3.
                                    </span>
                                    <span>

                                        Branding
                                    </span>
                                </span>
                            </template>
                            <div class="box box-dumb">
                                <div class="media ">
                                    <div class="media-left">

                                        <b-upload drag-drop>
                                            <div class=" px-4 py-4 has-text-centered">
                                                <p>
                                                    <b-icon icon="image-plus" class="has-text-grey-light">
                                                    </b-icon>
                                                </p>
                                            </div>

                                        </b-upload>
                                    </div>
                                    <div class="media-content">
                                        <p class="has-text-weight-semibold">Add your Favicon</p>
                                        <p class="">This is will be used as your app icon on the Customers phone</p>
                                        <p class="heading">124x124 Dimensions Required</p>
                                    </div>
                                </div>
                                <div class="media ">
                                    <div class="media-left">

                                        <b-upload drag-drop>
                                            <div class=" px-6 py-4 has-text-centered">
                                                <p>
                                                    <b-icon icon="image-plus" class="has-text-grey-light">
                                                    </b-icon>
                                                </p>
                                            </div>

                                        </b-upload>
                                    </div>
                                    <div class="media-content">
                                        <p class="has-text-weight-semibold">Add your Company Logo</p>
                                        <p class="">This is will be used with your brand placements - Invoice etc.</p>
                                        <!-- <p class="heading">124x124 Dimensions Required</p> -->
                                    </div>
                                </div>

                                <br>
                                <div class="level is-mobile">
                                    <div class="level-left">
                                        <div class="level-item">
                                            <button @click="() => { pageTab = 'bank' }" class="button ">
                                                <b-icon class="mr-2" icon="chevron-left"></b-icon>
                                                Previous
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
                        </b-tab-item>
                    </b-tabs>

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