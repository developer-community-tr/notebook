<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-12">
          <card>
            <template slot="header">
              <h4 class="card-title">Time Definitions</h4>
              <p class="card-category">Time definitions for learning grammar.</p>
            </template>
            <div class="typo-line">
              <h6>
                <p class="category">Header 6</p>Light Bootstrap Table Heading
              </h6>
            </div>
            <div class="typo-line">
              <p><span class="category">Paragraph</span>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed
                diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim
                veniam.
              </p>
            </div>
          </card>
        </div>

      </div>
    </div>
  </div>
</template>
<script>
import Card from 'src/components/Cards/Card.vue'

export default {
  components: {
    Card
  }
}

</script>
<style>

</style>
