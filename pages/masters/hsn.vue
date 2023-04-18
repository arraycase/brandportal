<template>
    <div class="container">
        <b-loading :active.sync="loading"></b-loading>

        <p class="is-size-5 has-text-weight-semibold">HSN Master</p>
        <br />

        <b-modal :active.sync="modal">
            <div class="card">
                <div class="card-content">
                    <div class="content">
                        <p class="has-text-weight-bold is-size-5">Edit HSN</p>
                        <div class="control">
                            <b-field label="HSN" :type="{ 'is-danger': edit.errors.name }">
                                <b-input v-model="edit.name" ref="editname" placeholder="Enter HSN" />
                            </b-field>
                            <b-field label="Description">
                                <b-input type="textarea" maxlength="250" v-model="edit.description"
                                    placeholder="HSN Description" />
                            </b-field>
                        </div>
                    </div>
                </div>
                <footer class="card-footer">
                    <a class="card-footer-item" @click="saveEditData">
                        <b-icon icon="refresh" class="mr-3"></b-icon>
                        <span>Update</span>
                    </a>
                    <a class="card-footer-item has-text-grey" @click="modal = !modal">
                        <b-icon class="mr-3" icon="close"></b-icon>
                        <span>Close</span>
                    </a>
                </footer>
            </div>
        </b-modal>

        <!-- Entry Form -->
        <div class="" v-show="view">
            <form id="data_entry" class="animated fadeIn" novalidate="true" @submit="submitData;">
                <div class="columns">
                    <div class="column">
                        <div class="control">
                            <b-field label="Name" :type="{ 'is-danger': errors.name }">
                                <b-input expanded type="text" v-model="form.name" ref="name"
                                    placeholder="Enter HSN e.g 520861" />
                            </b-field>
                            <b-field label="Description">
                                <template #label>
                                    <span>Description</span>
                                    <span class="tag is-rounded ml-2">
                                        <span class="has-text-grey">
                                            <b-icon icon="help-circle" class="mr-1" size="is-small"></b-icon>
                                            Enter each description in new line
                                        </span>
                                    </span>
                                </template>
                                <b-input type="textarea" maxlength="250" v-model="form.description"
                                    placeholder="HSN Description e.g Cotton Fabric silk rugs " />
                            </b-field>
                        </div>
                        <p class="has-text-danger  is-underlined" v-if="Object.keys(errors).length != 0">
                            <b-icon icon="alert-circle" class="mr-2"></b-icon>
                            <span>Please Fix Errors</span>
                        </p>
                        <br />
                        <div class="field is-grouped">
                            <div class="control">
                                <button type="submit" @click.prevent="submitData" class="button is-link">
                                    <b-icon class="mr-3" icon="check"></b-icon>
                                    <span>Save</span>
                                </button>
                            </div>
                            <div class="control">
                                <button class="button"
                                    @click.prevent="
                                        view = !view;
                                    loadAsyncSearch();
                                                                                                                                                                                                                                                                                                                                                                                                                                                                ">
                                    <b-icon class="mr-3" icon="eye"></b-icon>
                                    <span>View</span>
                                </button>
                            </div>

                        </div>
                    </div>
                </div>
            </form>
        </div>

        <!-- Table  -->

        <div v-show="!view">
            <div>


                <div class="">
                    <b-field has-addons grouped expanded>
                        <b-field>
                            <button class="button is-link" @click.prevent="view = !view">
                                <b-icon icon="plus" class="mr-2"></b-icon>
                                <span>Add</span>
                            </button>
                        </b-field>
                        <p class="control">
                            <b-field label="Show" label-position="on-border">
                                <b-select @input="loadAsyncSearch" v-model="showItems">
                                    <option value="20">20</option>
                                    <option value="40">40</option>
                                    <option value="60">60</option>
                                    <option value="80">80</option>
                                    <option value="100">100</option>
                                </b-select>

                            </b-field>
                        </p>
                        <b-field label="Search" expanded label-position="on-border">
                            <b-input @keyup.enter.native="loadAsyncSearch" placeholder="Search" v-model="query_search"
                                expanded icon="magnify"></b-input>
                        </b-field>

                        <!-- <p class="control" style="width: 100%">
                            <label for="" class="heading">Search</label>

                        </p> -->
                    </b-field>

                    <b-table paginated backend-pagination @page-change="onPageChange" :per-page="showItems"
                        @change="onPageChange" :current.sync="currentPage" :pagination-simple="false"
                        :pagination-position="'bottom'" :data="data" :loading="loading" :range-before="3" :range-after="1"
                        :total="totalItems" v-model="currentPage">
                        <template>
                            <b-table-column v-slot="props" field="name" label="Name">{{
                                props.row.name
                            }}</b-table-column>
                            <b-table-column v-slot="props" field="description" label="Description">
                                <ol>
                                    <li :key="index" v-for="(row, index) in props.row.description.split('\n')">
                                        {{ row }}
                                    </li>
                                </ol>
                            </b-table-column>
                            <b-table-column v-slot="props" field label="More">
                                <div class="buttons">
                                    <button @click.prevent="editData(props.row, props.row.id)"
                                        class="button is-info is-light">
                                        Edit
                                    </button>
                                    <button @click="deleteData(props.row, props.index)" class="button is-danger is-light">
                                        <b-icon icon="delete"></b-icon>
                                    </button>
                                </div>
                            </b-table-column>
                        </template>
                        <template slot="empty">
                            <div class="has-text-centered has-text-grey-light my-6">

                                <!-- <b-icon icon="file-plus" size="is-large"></b-icon> -->
                                <br />
                                <p class="is-size-5 ">
                                    Nothing to show.
                                    <br />Add some data
                                </p>
                                <br>
                                <button class="button" @click="view = !view">
                                    <b-icon icon="plus" class="mr-2"></b-icon>
                                    Add Data</button>
                            </div>
                        </template>
                    </b-table>
                </div>
            </div>
        </div>
    </div>
</template>
<script>

export default {
    layout: "portal",
    data() {
        return {
            view: true,
            form: {
                name: null,
                description: null,
            },
            errors: {},
            isSubmitting: false,
            data: [],
            loading: false,
            modal: false,
            edit: {
                errors: {},
                name: null,
                description: null,
                index: null,
            },
            query_search: "",
            currentPage: 1,
            showItems: 20,
            totalItems: null,
            query_search: null,
            search_filter: null,
        };
    },
    computed: {
        autocompleteData() {
            if (this.data.length != 0) {
                if (this.query_search == "") {
                    return this.data;
                } else {
                    return this.data.filter((option) => {
                        return (
                            option.name
                                .toString()
                                .toLowerCase()
                                .indexOf(this.query_search.toLowerCase()) >= 0
                        );
                    });
                }
            }
        },
    },

    mounted() {
        this.$refs.name.focus();
    },
    methods: {
        checkData(e) {
            this.errors = {};

            if (this.form.name) {
                return true;
            }
            if (!this.form.name) {
                this.$set(this.errors, "name", true);
            }
        },

        submitData(e) {
            let self = this;
            this.isSubmitting = true;
            if (this.checkData()) {
                this.$axios
                    .post("/basic_master/add/hsn", this.form)
                    .then(function (response) {
                        self.isSubmitting = false;
                        if (response.data.success) {
                            self.form.name = null;
                            self.form.description = null;

                        }
                        self.$buefy.snackbar.open({
                            duration: 4000,
                            message: response.data.message || response.data.success,
                            type: "is-light",
                            position: "is-top-right",
                            actionText: "Close",
                            queue: true,
                            onAction: () => {
                                self.isActive = false;
                            },
                        });
                    })
                    .catch(function (error) {
                        self.isSubmitting = false;
                        console.log(error);
                        self.$buefy.snackbar.open({
                            duration: 4000,
                            message: "Unable to save Data.",
                            type: "is-light",
                            position: "is-top-right",
                            actionText: "Close",
                            queue: true,
                            onAction: () => {
                                self.isActive = false;
                            },
                        });
                    });
            }
        },
        loadAsyncSearch(args = null) {
            if (args == "category") {
                this.currentPage = 1;
            }
            this.loading = true;
            let params = [
                `page=${this.currentPage}`,
                `show=${this.showItems}`,
                `query=${this.query_search}`,
            ].join("&");

            this.$axios
                .get(`/basic_master/get/hsn?${params}`)
                .then((response) => {
                    this.data = response.data.data;
                    this.totalItems = response.data.count;
                })
                .catch((error) => {
                    this.data = [];
                    this.totalItems = 0;
                    this.loading = false;
                    throw error;
                })
                .finally(() => {
                    this.loading = false;
                });
        },
        onPageChange(page) {
            this.currentPage = page;

            this.loadAsyncSearch();
            // }
        },

        editData(data, index) {
            this.edit.errors = {};

            this.modal = true;
            this.edit.name = data.name;
            this.edit.description = data.description;
            this.edit.id = data.id;
            this.edit.index = index;
        },
        saveEditData(e) {
            let self = this;
            let dataList = this.data;
            this.edit.errors = {};

            if (this.edit.name) {
                this.$axios
                    .post("/basic_master/edit/hsn", this.edit)
                    .then(function (response) {
                        if (response.data.success) {
                            dataList = self.data.filter(function (x) {
                                return x.id === self.edit.id;
                            });
                            dataList[0].name = self.edit.name;
                            dataList[0].description = self.edit.description;
                            self.modal = !self.modal;

                            self.$buefy.snackbar.open({
                                duration: 4000,
                                message: response.data.success,
                                type: "is-light",
                                position: "is-top-right",
                                actionText: "Close",
                                queue: true,
                                onAction: () => {
                                    self.isActive = false;
                                },
                            });
                        } else {
                            if (response.data.message) {
                                self.$buefy.snackbar.open({
                                    duration: 4000,
                                    message: response.data.message,
                                    type: "is-light",
                                    position: "is-top-right",
                                    actionText: "Close",
                                    queue: true,
                                    onAction: () => {
                                        self.isActive = false;
                                    },
                                });
                            }
                        }
                    })
                    .catch(function (error) {
                        console.log(error);
                        if (response.data.message) {
                            self.$buefy.snackbar.open({
                                duration: 4000,
                                message: "Unable to save data",
                                type: "is-light",
                                position: "is-top-right",
                                actionText: "Close",
                                queue: true,
                                onAction: () => {
                                    self.isActive = false;
                                },
                            });
                        }
                    });
                return true;
            }

            if (!this.edit.name) {
                this.$set(this.edit.errors, "name", true);
            }
        },
        exportData(data) {
            this.isDownloading = true;
            this.$axios
                .get("/basic_master/export/" + String(data))
                .then((response) => {
                    var fileURL = window.URL.createObjectURL(new Blob([response.data]));
                    var fileLink = document.createElement("a");

                    fileLink.href = fileURL;
                    fileLink.setAttribute("download", data + ".csv");
                    document.body.appendChild(fileLink);

                    fileLink.click();
                })
                .finally(() => (this.isDownloading = false));
        },


        deleteData(data, index) {
            let dataList = this.data;
            let self = this;
            this.$axios
                .post("/basic_master/delete/hsn", data)
                .then(function (response) {
                    if (response.data.success) {
                    }
                    dataList.splice(index, 1);
                    self.$buefy.snackbar.open({
                        duration: 4000,
                        message: response.data.success || response.data.message,
                        type: "is-light",
                        position: "is-top-right",
                        actionText: "Close",
                        queue: true,
                        onAction: () => {
                            self.isActive = false;
                        },
                    });
                })
                .catch(function (error) {
                    console.log(error);
                    self.$buefy.snackbar.open({
                        duration: 4000,
                        message: "Unable to delete Data",
                        type: "is-light",
                        position: "is-top-right",
                        actionText: "Close",
                        queue: true,
                        onAction: () => {
                            self.isActive = false;
                        },
                    });
                });
        },
    },
};
</script>