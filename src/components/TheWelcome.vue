<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Documentation</template>

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent et lorem non dolor tempor eleifend vel sit amet sapien. Nulla tincidunt, purus non rhoncus auctor, sem elit semper justo, sed. 
  
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Tooling</template>

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent et lorem non dolor tempor eleifend vel sit amet sapien. Nulla tincidunt, purus non rhoncus auctor, sem elit semper justo, sed. 
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Ecosystem</template>

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent et lorem non dolor tempor eleifend vel sit amet sapien. Nulla tincidunt, purus non rhoncus auctor, sem elit semper justo, sed. 
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>Community</template>

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent et lorem non dolor tempor eleifend vel sit amet sapien. Nulla tincidunt, purus non rhoncus auctor, sem elit semper justo, sed. 
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading>Support Vue</template>

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent et lorem non dolor tempor eleifend vel sit amet sapien. Nulla tincidunt, purus non rhoncus auctor, sem elit semper justo, sed. 
  </WelcomeItem>
</template>
