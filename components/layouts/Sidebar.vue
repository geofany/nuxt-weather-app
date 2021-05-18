<template lang="html">
    <ul class="navbar-nav bg-gradient-primary sidebar sidebar-dark accordion" id="accordionSidebar">
        <nuxt-link class="sidebar-brand d-flex align-items-center justify-content-center" to="/">
            <div class="sidebar-brand-icon rotate-n-15">
                <i class="fas fa-cloud"></i>
            </div>
            <div class="sidebar-brand-text mx-3">WEATHER APP</div>
        </nuxt-link>
        <hr class="sidebar-divider my-0">
        <li class="nav-item active">
            <nuxt-link class="nav-link" to="/dashboard">
                <i class="fas fa-fw fa-tachometer-alt"></i>
                <span>Dashboard</span>
            </nuxt-link>
        </li>
        <hr class="sidebar-divider my-0">
        <li class="nav-item">
            <nuxt-link class="nav-link" to="/weather">
                <i class="fas fa-fw fa-cloud"></i>
                <span>Weather</span>
            </nuxt-link>
        </li>
        <!-- <div class="sidebar-heading">
            Interface
        </div>
        <li class="nav-item">
            <a class="nav-link collapsed" href="#" data-toggle="collapse" data-target="#collapseTwo" aria-expanded="true" aria-controls="collapseTwo">
                <i class="fas fa-fw fa-cog"></i>
                <span>Components</span>
            </a>
            <div id="collapseTwo" class="collapse" aria-labelledby="headingTwo" data-parent="#accordionSidebar">
                <div class="bg-white py-2 collapse-inner rounded">
                    <h6 class="collapse-header">Custom Components:</h6>
                    <a class="collapse-item" href="buttons.html">Buttons</a>
                </div>
            </div>
        </li> -->
    </ul>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
</style>
