<script setup>
import FigureSection from './FigureSection.vue'
</script>

<template>
  <FigureSection
    title="Case Study"
    src="resources/case_study.png"
    alt="Case study comparing predictions from DeepSeek-V4-Pro, Gemini-3-Flash, and AgentForesight-7B"
  >
    <template #caption>
 While the <strong>direct prediction baseline</strong> only predicts FM-3.1 and misses the true failure modes,
  VerifyMAS successfully identifies the <strong>key ground-truth errors</strong>, including
  <strong>FM-1.4, FM-2.4, and FM-3.2</strong>.
  This example shows that VerifyMAS can better capture
  <strong>trajectory-level, context-dependent failures</strong> than direct prediction methods.
    </template>
  </FigureSection>
</template>
