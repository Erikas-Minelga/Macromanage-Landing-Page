<script setup>

</script>

<template>
    <footer>
        <div class="text-center white-txt large-text">
            Macromanage
        </div>
        <div id="footer-links" class="flex-row">
            <div class="white-txt">
                <p class="text-center bold-txt">Sitemap</p>
                <ul>
                    <li><a href="#" class="white-txt">Home</a></li>
                    <li><a href="#" class="white-txt">Features</a></li>
                    <li><a href="#" class="white-txt">Pricing</a></li>
                    <li><a href="#" class="white-txt">Resources</a></li>
                </ul>
            </div>
            <div class="white-txt">
                <p class="text-center bold-txt">Community</p>
                <ul>
                    <li><a href="#" class="white-txt">Blog</a></li>
                    <li><a href="#" class="white-txt">Webinars</a></li>
                    <li><a href="#" class="white-txt">Forum</a></li>
                </ul>
            </div>
            <div class="white-txt">
                <p class="text-center bold-txt">Company</p>
                <ul>
                    <li><a href="#" class="white-txt">About Us</a></li>
                    <li><a href="#" class="white-txt">Contact Us</a></li>
                    <li><a href="#" class="white-txt">Privacy Policy</a></li>
                    <li><a href="#" class="white-txt">Terms of Service</a></li>
                </ul>
            </div>
        </div>
    </footer>
</template>

<style scoped>
    footer{
        background-color: #202020;
        height: 212px;
    }

    #footer-links{
        column-gap: 55px;
        margin-top: 15px;
    }

    ul{
        margin-top: 10px;
    }

    li{
       list-style: none;
       text-align: center;
    }
</style>