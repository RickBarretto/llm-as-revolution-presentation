<script setup>
defineProps({
  /**
   * Sequência de etapas, na ordem em que devem aparecer.
   * Ex: :steps="['Entrada', 'Tokenização', 'Embeddings']"
   */
  steps: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <div class="flow" :style="{ '--count': steps.length }">
    <template v-for="(step, i) in steps" :key="i">
      <div class="flow-node" :style="{ '--i': i }">
        {{ step }}
      </div>
      <div v-if="i < steps.length - 1" class="flow-connector" :style="{ '--i': i }" aria-hidden="true">
        <svg viewBox="0 0 24 24" width="16" height="16">
          <path
            d="M12 3 L12 17 M6 11 L12 17 L18 11"
            fill="none"
            stroke="currentColor"
            stroke-width="1.6"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </div>
    </template>
  </div>
</template>

<style scoped>
.flow {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  max-height: 100%;
  overflow: hidden;
  box-sizing: border-box;
  padding: 0.5rem 0;
}

.flow-node {
  font-size: clamp(0.85rem, calc(2.1rem - 0.16rem * var(--count)), 1.35rem);
  font-weight: 600;
  letter-spacing: -0.01em;
  padding: 0.4em 1.2em;
  border-radius: 999px;
  border: 1px solid color-mix(in srgb, currentColor 22%, transparent);
  background: color-mix(in srgb, currentColor 6%, transparent);
  white-space: nowrap;
  line-height: 1.2;
  opacity: 0;
  animation: flow-rise 0.5s cubic-bezier(0.2, 0.7, 0.3, 1) forwards;
  animation-delay: calc(var(--i) * 130ms);
}

.flow-connector {
  display: flex;
  align-items: center;
  justify-content: center;
  height: clamp(0.8rem, calc(1.5rem - 0.11rem * var(--count)), 1.2rem);
  color: currentColor;
  opacity: 0;
  animation: flow-fade 0.4s ease forwards;
  animation-delay: calc(var(--i) * 130ms + 90ms);
}

.flow-connector svg {
  width: clamp(11px, calc(18px - 0.8px * var(--count)), 16px);
  height: auto;
}

.flow-connector svg {
  opacity: 0.55;
}

@keyframes flow-rise {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes flow-fade {
  from {
    opacity: 0;
  }
  to {
    opacity: 0.55;
  }
}

@media (prefers-reduced-motion: reduce) {
  .flow-node,
  .flow-connector {
    animation: none !important;
    opacity: 1 !important;
  }
}
</style>