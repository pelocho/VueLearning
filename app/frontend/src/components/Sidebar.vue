<template>
    <div class="sidebar">
        <div class="sidebar-backdrop"></div>
        <transition name="slide">
            <div class="sidebar-panel">
                <slot></slot>
            </div>
        </transition>
    </div>
</template>
<script>

    export default {
    }
</script>
<style>
    .slide-enter-active,
    .slide-leave-active
    {
        transition: transform 0.2s ease;
    }

    .slide-enter,
    .slide-leave-to {
        transform: translateX(-100%);
        transition: all 150ms ease-in 0s
    }

    .sidebar-backdrop {
        background-color: rgba(0,0,0,.5);
        width: 100vw;
        height: 100vh;
        position: fixed;
        top: 0;
        left: 0;
        cursor: pointer;
    }

    .sidebar-panel {
        overflow-y: auto;
        background-color: rgba(34, 169, 80, 1);
        position: fixed;
        right: 0;
        top: 0;
        height: 100vh;
        z-index: 999;
        padding: 3rem 20px 2rem 20px;
        width: 400px;
    }
</style>