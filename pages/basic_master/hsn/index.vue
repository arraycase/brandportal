<template>

  <div>
    <div class="level is-mobile">
      <div class="level-left">
        <div class="level-item">
          <div>

            <p class="is-size-5 has-text-weight-semibold">HSN Master</p>
            <p class="is-size-6">Create HSN for tax purpose</p>

          </div>
        </div>
      </div>
      <div class="level-right">
        <div class="level-item">
          <n-link to="/basic_master/hsn/add"  class="button">
            <b-icon class="mr-2" icon="plus"></b-icon>
            Add</n-link>
        </div>
      </div>
    </div>
    <div class="box box-dumb">

      <b-table :data="[]">
        <template slot="empty">
          <div class="py-6 has-text-centered">

            <p>No Data has been added.</p>
            <p>Create one now.</p>
            <br>
            <n-link to="/basic_master/hsn/add" class="button is-link"><b-icon class="mr-2" icon="plus"></b-icon>
              Add</n-link>
          </div>
        </template>
      </b-table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Company',
  layout: 'portal'
}
</script>

<style>

</style>