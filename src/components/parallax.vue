<template>
<v-parallax
    dark
    :src="require(`../assets/${picture}.jpeg`)"
    height="300"
>
<v-row
    align="center"
    justify="center"

>
  <v-col class="text-center" cols="12">
    <h1 class="font-weight-bold mb-4"
    style="color: black; font-size: 7em"
    >{{title}}</h1>
  </v-col>
</v-row>
</v-parallax>
</template>

<script>
export default {
  props: ['picture','title']
}

</script>
