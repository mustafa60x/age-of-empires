<template>
  <div>
    <div>
      <div
        class="unit-section-title mb-3 mt-6 text-2xl"
        style="display: flex; justify-content: flex-start"
      >
        Ages
      </div>
      <div class="flex justify-center items-baseline">
        <div class="flex flex-wrap">
          <FilterButton
            v-for="button in filterButtons"
            :key="button"
            :filterMethod="filterMethod"
            :text="button.text"
            :value="button.value"
            :activeBtn="activeBtn"
          ></FilterButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FilterButton from "@/components/units/ages/FilterButton";
export default {
  components: {
    FilterButton,
  },
  data() {
    return {
      activeBtn: "All",
      filterButtons: [
        {
          text: "All",
          value: "All",
        },
        {
          text: "Dark",
          value: "Dark",
        },
        {
          text: "Feudal",
          value: "Feudal",
        },
        {
          text: "Castle",
          value: "Castle",
        },
        {
          text: "Imperial",
          value: "Imperial",
        },
      ],
    };
  },
  methods: {
    filterMethod(age) {
      this.activeBtn = age;
      this.$emit("listUnits", age);
    },
  },
};
</script>
