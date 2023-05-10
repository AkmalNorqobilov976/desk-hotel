<template>
    <div id="Navbar" class="flex items-center justify-space-between">
        <div class="navbar-brand">
            <a href="#"><img src="./../assets/images/logo.png" alt=""></a>
        </div>
        <ul class="nav-list flex items-center">
            <li class="nav-list__item">
            </li>
            <li class="nav-list__item active">
                Home
            </li>
            <li class="nav-list__item">
                Property
            </li>
            <li class="nav-list__item">
                Property
            </li>
            <li class="nav-list__item">
                <Dropdown label="Property"/>
            </li>
            <li>
                <Btn :label="'Signup!'"/>
            </li>
        </ul>
    </div>
</template>

<script>
import Btn from './Btn.vue'
import Dropdown from './Dropdown.vue'
export default {
  components: { 
    Btn,
    Dropdown
  },
    
}
</script>