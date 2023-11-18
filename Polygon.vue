<template>
  <div class="card mt60">
    <GoogleMap
      api-key="YOUR_GOOGLE_MAPS_API_KEY"
      style="width: 100%; height: 500px"
      :center="center"
      :zoom="5"
    >
      <Polygon :options="bermudaTriangle" />
      <Marker :options="{ position: center }" />

      <InfoWindow :options="{ position: center, content: '<strong>Us population density</strong><p>Montana 6.58</p> <span>people per sqaure mile</span>' }" class="data-info" />
    </GoogleMap>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { GoogleMap, Polygon, Marker,InfoWindow } from "vue3-google-map";

export default defineComponent({
  components: { GoogleMap, Polygon,Marker,InfoWindow  },
  data() {
    
    const center = { lat: 24.886, lng: -70.268 };
    const triangleCoords = [
      { lat: 25.774, lng: -80.19 },
      { lat: 18.466, lng: -66.118 },
      { lat: 32.321, lng: -64.757 },
      { lat: 25.774, lng: -80.19 },
    ];
    const bermudaTriangle = {
      paths: triangleCoords,
      strokeColor: "#FF0000",
      strokeOpacity: 0.8,
      strokeWeight: 2,
      fillColor: "#FF0000",
      fillOpacity: 0.35,
    };

    return { center, bermudaTriangle };
  },
});
</script>