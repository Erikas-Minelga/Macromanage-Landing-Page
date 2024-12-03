<script setup>
    import { ref } from 'vue';

    const menuVisible = ref(false);
    const menuElem = ref(null);

    function toggleMenu(event){
        menuVisible.value = !menuVisible.value;

        if(menuVisible.value)
            menuElem.value.focus();
    }

    function closeMenuOnLostFocus(){
        menuVisible.value = false;
    }
</script>

<template>
    <nav>
        <div class="burger-menu" @click="toggleMenu">
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
        </div>
        <a href="#"><img src="/img/macromanage_logo.png"></a>
        <div id="menu" ref="menuElem" :class="menuVisible ? 'mobile-menu-open' : 'mobile-menu-closed'" tabindex="0" @blur="closeMenuOnLostFocus">
            <ul class="links">
                <li><a href="#">Features</a></li>
                <li><a href="#">Pricing</a></li>
                <li><a href="#">Resources</a></li>
            </ul>
            <ul class="buttons">
                <a href="#"><li class="white-btn">Log in</li></a>
                <a href="#"><li class="blue-btn">Create Account</li></a>
            </ul>
        </div>
    </nav>
</template>

<style scoped>
    .bar{
        width: 36px;
        height: 7px;
        margin: 5px 0 5px 0;
        background-color: #A09E9E;
    }

    .burger-menu{
        display: none;
    }

    nav{
        height: 47px;
        position: sticky;
        top: 0;
        background-color: #FFFFFF;
        z-index: 2;
    }

    nav, #menu{
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
    }

    #menu{
        flex-basis: 70%;
    }

    @media screen and (max-width: 850px){
        
        .mobile-menu-open{
            width: 45vw;
            opacity: 1;
        }

        .mobile-menu-closed{
            width: 0;
            opacity: 0;
        }

        nav{
            justify-content: space-between;
        }

        .burger-menu{
            display: block;
            margin-left: 15px;
            z-index: 2;
        }

        #menu{
            flex-direction: column;
            position: absolute;
            top: 47px;
            left: 0px;
            height: 40vh;
            z-index: 1;
            background-color: white;
            border: 1px solid black;
            transition: transform 1s linear;
        }

        ul{
            display: flex;
            flex-direction: column;
            row-gap: 20px;
        }
    }

    li{
        display: inline-block;
        margin: 0 12.5px 0 12.5px;
    }

    .buttons > a > li{
        height: 42px;
        width: 136px;
        text-align: center;
        line-height: 42px;
    }

    img{
        height: 47px;
        z-index: 0;
    }
</style>