<script setup>
import FigureSection from './FigureSection.vue'
</script>

<template>
  <FigureSection
    title="Fine-grained Failure Analysis"
    src="resources/ablation_analysis.png"
    alt="Stage-wise ablation and deployment trade-off"
  >
    <template #caption>
 VerifyMAS consistently improves <strong>error detection</strong> across all three categories
  compared with the DPR and CoT-Agent. The improvement is especially pronounced on
  <strong>Global and Hybrid Errors</strong>, showing that the proposed
  <strong>error-first</strong> and <strong>hypothesis-verification</strong> design is particularly
  effective at capturing failures that only become evident from the full interaction trajectory.
    </template>
  </FigureSection>
</template>
