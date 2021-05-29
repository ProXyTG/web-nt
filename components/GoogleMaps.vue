<template>
  <div>
    <GMap
      ref="gMap"
      language="en"
      :cluster="{options: {styles: clusterStyle}}"
      :center="{lat: locations[0].lat, lng: locations[0].lng}"
      :options="{fullscreenControl: false, styles: mapStyle}"
      :zoom="18"
      >
        <GMapMarker
          v-for="location in locations"
          :key="location.id"
          :position="{lat: location.lat, lng: location.lng}"
          :options="{icon: location === currentLocation ? pins.selected : pins.notSelected}"
          @click="currentLocation = location"
         >
          <GMapInfoWindow :options="{maxWidth: 200}">
            <code>
              <a href="https://www.google.com/maps/place/Notus/@45.7874971,16.0261506,17z/data=!3m1!4b1!4m5!3m4!1s0x476679e4631b5479:0xf397a6cfa8839863!8m2!3d45.7874926!4d16.0282696" target="_blank">
                Notus
              </a>
            </code>
          </GMapInfoWindow>
        </GMapMarker>
      <GMapCircle :options="circleOptions"/>
    </GMap>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentLocation: {},
      circleOptions: {},
      locations: [
        {
          lat: 45.78832,
          lng: 16.02869
        }
      ],
      pins: {},
      mapStyle: [],
      clusterStyle: [
        {
          url: "https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/m1.png",
          width: 56,
          height: 56,
          textColor: "#fff"
        }
      ]
    }
  }
}
</script>

<style lang="scss">

</style>
