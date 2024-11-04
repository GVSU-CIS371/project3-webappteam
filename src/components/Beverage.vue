<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer :name="creamer?.name!" :color="creamer?.color!"/>
        <!-- I think we can throw a v-if here to check and set the color-->
        <!-- adding the ! at the ends forces not null -->
      </template>
      <template v-slot:mid>
        <Syrup :name="syrup?.name!" :color="syrup?.color!"/>
        <!-- I think we can throw a v-if here to check and set the color-->
        <!-- adding the ! at the ends forces not null -->
      </template>
      <template v-slot:bottom>
        <Base :name="base?.name!" :color="base?.color!" />
        <!-- adding the ! at the ends forces not null -->
      </template>
    </Contents>
  </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
  isIced: boolean;
  base: { name: string; color: string } | null;
  creamer: { name: string; color: string } | null;
  syrup: { name: string; color: string } | null;
};
defineProps<Props>();
</script>