<template>
    <div id="Footer">
        <img src="./../assets/images/logo.png" alt="">
        <div class="footer-body flex justify-space-between">
            <div class="footer-body__subscribe">
                <p class="footer-body__subscribe--title">
                    We provide information about properties such as houses,
                    villas and apartments to help people find their dream home
                </p>
                <h3 class="footer-body__subscribe--label">
                    Subscribe to our newsletter!
                </h3>
                <TextField v-model="salom" placeholder="Your email here">
                    <template #prepend>
                        <EmailIcon/>
                    </template>
                    <template #append>
                        <Btn :label="'Subsribe Now'"/>
                    </template>
                </TextField>
            </div>
            <div class="flex justify-space-between flex-1">
                <div class="footer-body__property">
                    <FooterList :title="'Property'" :lists="[
                        'House', 'Apartment', 'Villa'
                    ]"/>
                </div>
                <div class="footer-body__article">
                    <FooterList :title="'Article'" :lists="[
                        'New Article', 'Popular Article', 'Most Read', 'Tips & Tricks'
                    ]"/>
                </div>
                <div class="footer-body__contact">
                    <FooterList :title="'Contact'" :lists="[
                        'Medan, South Sumatera', '(62) 81312120001', 'halo@homedesk.com'
                    ]"/>
                </div>
            </div>
        </div>
        <div class="footer flex justify-space-between items-center">
            <div class="footer__privacy flex items-center">
                <p>
                    Terms & Conditions
                </p>
                <p>
                    Privacy Policy
                </p>
            </div>
            <div class="footer__icons flex items-center">
                <span>
                    <FacebookIcon/>
                </span>
                <span>
                    <TwitterIcon/>
                </span>
                <span>
                    <InstagramIcon/>
                </span>
            </div>
        </div>
    </div>
</template>
<script>
import Btn from './Btn.vue'
import FooterList from './FooterList.vue'
import TextField from './TextField.vue'
export default {
    components: {
        TextField,
        Btn,
        FooterList
    },
    data: () => ({
        salom: "asdfasdf"
    })
}
</script>