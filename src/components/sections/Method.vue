<script setup>
import FigureSection from './FigureSection.vue'
</script>

<template>
  <FigureSection
    title="Method"
    src="resources/pipeline.png"
    alt="AgentForesight pipeline: AFTraj-2K construction and coarse-to-fine training"
  >
    <template #caption>
   <p>
  <strong>(a) Zero-shot inference.</strong> A trajectory is paired with hypotheses on
  <strong>predefined error types</strong>, and then an LLM predicts whether the trajectory is
  “entail”, “neutral”, or “contradict” w.r.t. each hypothesis describing the presence of an error type.
  The <strong>entailed hypotheses</strong> are further examined for
  <strong>faulty agent attribution</strong>, producing the final error–agent predictions.
</p>

<p>
  <strong>(b) Hypothesis verification-guided supervised fine-tuning.</strong>
  We construct trajectory–hypothesis pairs by pairing each trajectory with both annotated errors
  and absent errors. VerifyMAS is then fine-tuned to
  <strong>jointly predict the type of the error and the responsible agent</strong>.
</p>
    </template>
  </FigureSection>
</template>
