<template>
    <aside :class="`${is_expanded && 'is-expanded'}`">
        <div class="logo">
            <img src="../assets/logo.png" alt="Waou">
        </div>

        <div class="menu-toggle-wrap">
            <button class="menu-toggle" @click="ToggleMenu">
                <span class="material-icons">
                    keyboard_double_arrow_right
                </span>
            </button>
        </div>
    </aside>
</template>


<script>
import {ref} from 'vue'
export default{
    name: 'SideBar'
}

const is_expanded = ref(false)

const ToggleMenu = () => {
    is_expanded.value = !is_expanded.value
}
</script>


<style lang="scss" scoped>
aside {
    display: flex;
    flex-direction: column;
    width: calc(2rem + 32px);
    min-height: 100vh;
    overflow: hidden;
    padding: 1rem;

    background-color: var(--dark);
    color: var(--light);

    transition: 0.2s ease-out;

    .logo{
        margin-bottom: 1rem;
        img{
            width: 2rem;
        }
    }

    @media(max-width: 768px){
        position: fixed;
        z-index: 99;
    }
}
</style>
