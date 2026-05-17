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
      <b>(a)</b>Our hypothesis verification-based approach VerifyMAS vs. two existing approaches. <br>
      <b>(b)</b> Performance of three approaches on Aegis-Bench \cite{kong2025aegis} in attributing three categories of error types—global, local, and hybrid errors in average Pair-F1 <br>
    </template>
  </FigureSection>
</template>
