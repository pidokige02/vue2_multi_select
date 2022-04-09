<template>
  <div>
    <div>
      <label class="typo__label">Single select</label>
      <multiselect v-model="value0" :options="options0" :searchable="false" :close-on-select="false" :show-labels="false" placeholder="Pick a value"></multiselect>
      <pre class="language-json"><code>{{ value0  }}</code></pre>
    </div>

    <div>
      <label class="typo__label">Single select / dropdown</label>
      <multiselect v-model="value" deselect-label="Can't remove this value" track-by="name" label="name" placeholder="Select one" :options="options" :searchable="false" :allow-empty="false">
        <template slot="singleLabel" slot-scope="{ option }"><strong>{{ option.name }}</strong> is written in<strong>  {{ option.language }}</strong></template>
      </multiselect>
      <pre class="language-json"><code>{{ value  }}</code></pre>
    </div>
  </div>
</template>

<script>
  import Multiselect from 'vue-multiselect'

  export default {
    name: 'Multi',
    // OR register locally
    components: { Multiselect },
    data () {
      return {
      value0: '',
      options0: ['Select option', 'options', 'selected', 'mulitple', 'label', 'searchable', 'clearOnSelect', 'hideSelected', 'maxHeight', 'allowEmpty', 'showLabels', 'onChange', 'touched'],

      value: null, // data for Single select / dropdown
      options: [
        { name: 'Vue.js', language: 'JavaScript' },
        { name: 'Rails', language: 'Ruby' },
        { name: 'Sinatra', language: 'Ruby' },
        { name: 'Laravel', language: 'PHP', $isDisabled: true },
        { name: 'Phoenix', language: 'Elixir' }
      ]
      }
    }
  }
</script>

<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>