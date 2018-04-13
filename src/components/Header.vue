<template>
  <div class="row">
      <div class="col-sm-12">
          <h2>Quotes Added</h2>
          <div class="progress-bar" role="progressbar" 
            aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
            :style="{width: ((quotesCount / maxQuotes) * 100) + '%'}">
                {{ quotesCount }} / {{ maxQuotes }}
          </div>
      </div>
  </div>
</template>

<script>
export default {
  props: ["quotesCount", "maxQuotes"]
};
</script>

