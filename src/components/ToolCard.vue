<template>
  <router-link :to="tool.path">
    <c-card class="tool-card">
      <n-space justify="space-between" align="center">
        <n-icon class="icon" size="40" :component="tool.icon" />
        <n-space align="center">
          <n-tag
            v-if="tool.isNew"
            size="small"
            class="badge-new"
            round
            type="success"
            :bordered="false"
            :color="{ color: theme.primaryColor, textColor: theme.tagColor }"
          >
            New
          </n-tag>

          <favorite-button :tool="tool" />
        </n-space>
      </n-space>
      <n-h3 class="title">
        <n-ellipsis>{{ tool.name }}</n-ellipsis>
      </n-h3>

      <div class="description">
        <n-ellipsis :line-clamp="2" :tooltip="false" style="min-height: 44.78px">
          {{ tool.description }}
          <br />&nbsp;
        </n-ellipsis>
      </div>
    </c-card>
  </router-link>
</template>

<script setup lang="ts">
import type { Tool } from '@/tools/tools.types';
import { useThemeVars } from 'naive-ui';
import { toRefs } from 'vue';
import { useAppTheme } from '@/ui/theme/themes';
import FavoriteButton from './FavoriteButton.vue';

const props = defineProps<{ tool: Tool & { category: string } }>();
const { tool } = toRefs(props);
const theme = useThemeVars();

const appTheme = useAppTheme();
</script>

<style lang="less" scoped>
a {
  text-decoration: none;
}

.tool-card {
  transition: border-color ease 0.5s;
  border-width: 2px !important;
  color: transparent;

  &:hover {
    border-color: v-bind('appTheme.primary.colorHover');
  }

  .icon {
    opacity: 0.6;
    color: v-bind('theme.textColorBase');
  }

  .title {
    margin: 5px 0;
  }

  .description {
    opacity: 0.6;
    color: v-bind('theme.textColorBase');
    margin: 5px 0;
  }
}
</style>
