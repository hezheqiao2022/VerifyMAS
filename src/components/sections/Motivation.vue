<script setup>
import FigureSection from './FigureSection.vue'
</script>

<template>
  <FigureSection
    title="Why Hypothesis Verification?"
    src="resources/motivation.png"
    alt=""
  >
    <template #caption>
      <b>(a)</b> Our <b>hypothesis verification</b>-based approach VerifyMAS vs. two existing approaches. <br>
      <b>(b)</b> Performance of three approaches on <b>Aegis-Bench</b>  in attributing three categories of error types—<b>global, local, and hybrid</b> errors in average Pair-F1 <br>
    </template>
  </FigureSection>
</template>
