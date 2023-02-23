<template>
    <div class="backdrop">
        <div class="modal" :class= "{sale: theme === 'sale'}">
            <!-- <h1> {{ header }}</h1>
            <p>{{ text }}</p> -->
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Modal',
  props: ['theme']
}
</script>

<style scoped>
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: red;
        border-radius: 10px;
    }
    .modal.sale {
        background: purple;
        color: white;
    }
    .modal.sale h1{
        color: white;
    }
    .backdrop {
        height: 100%;
        width: 100%;
        top: 0;
        position: fixed;
        background: rgb(253, 250, 250);
    }
</style>