<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer
          v-if="props.creamer !== 'No Creamer'"
          :type="props.creamer"
        />
      </template>

      <template v-slot:mid>
        <Syrup
          v-if="props.syrup !== 'No Syrup'"
          :type="props.syrup"
        />
      </template>

      <template v-slot:bottom>
        <Base :type="props.base" />
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
  base: string;
  creamer: string;
  syrup: string;
};

const props = defineProps<Props>();
</script>
