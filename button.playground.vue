<template>
  <client-only>
    <span class="font-2-header text-color-1"> BUTTON </span>
    <div
      class="flex flex-col gap-4 p-4 bg-neutral-150 w-max border-dashed border-2 border-color-1 rounded-lg"
    >
      <div class="flex flex-row items-start gap-4">
        <button
          color="BLUE"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          color="BLUE"
          disabled
          text="Sign in interest list"
        />
        <button
          color="BLUE"
          :icon="LogoutIcon"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          color="BLUE"
          disabled
          :icon="LogoutIcon"
          text="Sign in interest list"
        />
      </div>

      <div class="flex flex-row items-start gap-4">
        <button
          color="VIOLET"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          color="VIOLET"
          disabled
          text="Sign in interest list"
        />
        <button
          color="VIOLET"
          :icon="LogoutIcon"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          color="VIOLET"
          disabled
          :icon="LogoutIcon"
          text="Sign in interest list"
        />
      </div>

      <div class="flex flex-row items-start gap-4">
        <button
          color="ORANGE"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          color="ORANGE"
          disabled
          text="Sign in interest list"
        />
        <button
          color="ORANGE"
          :icon="LogoutIcon"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          color="ORANGE"
          disabled
          :icon="LogoutIcon"
          text="Sign in interest list"
        />
      </div>

      <div class="flex flex-row items-start gap-4">
        <button
          filled
          color="BLUE"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          filled
          color="BLUE"
          disabled
          text="Sign in interest list"
        />
        <button
          filled
          color="BLUE"
          :icon="LogoutIcon"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          filled
          color="BLUE"
          disabled
          :icon="LogoutIcon"
          text="Sign in interest list"
        />
      </div>

      <div class="flex flex-row items-start gap-4">
        <button
          filled
          color="VIOLET"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          filled
          color="VIOLET"
          disabled
          text="Sign in interest list"
        />
        <button
          filled
          color="VIOLET"
          :icon="LogoutIcon"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          filled
          color="VIOLET"
          disabled
          :icon="LogoutIcon"
          text="Sign in interest list"
        />
      </div>

      <div class="flex flex-row items-start gap-4">
        <button
          filled
          color="ORANGE"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          filled
          color="ORANGE"
          disabled
          text="Sign in interest list"
        />
        <button
          filled
          color="ORANGE"
          :icon="LogoutIcon"
          text="Sign in interest list"
          @click="onClick"
        />
        <button
          filled
          color="ORANGE"
          disabled
          :icon="LogoutIcon"
          text="Sign in interest list"
        />
      </div>
    </div>
  </client-only>
</template>

<script lang="ts" setup>
import {
  ClientOnly,
} from '@/components/client-only/client-only';

import Button from '@/components/button/button.vue';

import LogoutIcon from '@/assets/icons/logout.svg?component';

function onClick() {
  // eslint-disable-next-line no-alert
  alert(
    'Los Angeles\' full name is "El Pueblo de Nuestra Senora la Reina de los Angeles de Porciuncula"',
  );
}
</script>
