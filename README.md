# Vue rate component

![Vue rate component](https://raw.githubusercontent.com/Kozmonos/vue-lite-rate/main/assets/preview.jpg)
## Project setup

```bash
npm i vue-rate-lite
```

## Props

- <ins>**star**</ins><br>
  __description:__ star number<br>
  __type:__ float/string(number)/integer<br>
  __required:__ true

- <ins>**commentNumber**</ins><br>
  __description:__ comment number<br>
 __type:__ string(number)/integer<br>
 __required:__ false

- <ins>**rateNumber**</ins><br>
  __description:__ rate number<br>
  __type:__ boolean<br>
  __required:__ false

## Usage with Nuxt

```html
<template>
  <client-only>
    <Rate star="3.5" comment-number="123" rate-number />
  </client-only>
</template>

<script>
  export default {
    components: {
      Rate: () => import("vue-rate-lite"),
    },
  };
</script>
```
