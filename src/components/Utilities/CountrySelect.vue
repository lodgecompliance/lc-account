<template>
    <v-autocomplete
        :items="countries"
        item-value="isoCode"
        item-text="name"
        v-bind="$attrs"
        v-on="$listeners"
    >
      <template #item="{ item: country, on }">
        <v-list-item v-on="on" dense>
          <v-list-item-avatar>
            <v-avatar>
              <span class="text-h5">{{ country.flag }}</span>
            </v-avatar>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title>{{country.name}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </template>
    </v-autocomplete>
</template>

<script>
import { Country }  from 'country-state-city';
export default {
  name: "CountrySelect",
  data() {
    return {}
  },
  computed: {
    countries() {
      return Country.getAllCountries()
    },
  }
}
</script>
