<template>
<div class="card mt60">
    <GoogleMap api-key="YOUR_GOOGLE_MAPS_API_KEY" style="width: 100%; height: 500px" :center="center" :zoom="15">
    <Marker :options="{ position: center }" />
    <InfoWindow :options="{ position: center, content: '<strong>Muhisnah</strong> <span>Jazz-influenced hip hop artist Mushinah <br>plays the Black Cat(1811 14th Street <br>NW) tonight with Exit Clov and Gods illa.<br>9:00 pm.$12. </span>' }" class="data-info" />
  </GoogleMap>
</div>
 
</template>


<script lang="ts">
import { defineComponent } from "vue";
import { GoogleMap, Marker,InfoWindow } from "vue3-google-map";

export default defineComponent({
  components: { GoogleMap, Marker, InfoWindow},
  data() {
    const center = {lat: 38.897957, lng:  -77.036560};
    const markerOptions = { position: center, label: "W", title: "Washington" };

    return { center, markerOptions };
  },
});
</script>