<template>
    <div class="oreo-flex__item">
        <slot></slot>
    </div>
</template>
<script>
import createBasic from 'oreo-ui/components/utils/create-basic'
export default createBasic({
    name: 'flex-item',
    props: {
    }
})
</script>
