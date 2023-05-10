<template>
    <header id="Header" class="flex">
        <div class="header-left">
            <h3 class="header-left__title">
                Good Living Better live <span>your dreams</span> easily here
            </h3>
            <div class="header-left__description">
                Everything you need about finding your place to live will be here, 
                where it will be easier for you. Our furniture is made from selected 
                and best quality materials that are suitable for your dream home
            </div>
            <div class="header-left__search flex items-center">
                <span class="header-left__search--location-i">
                    <LocationIcon/>
                </span>
                <input 
                    class="header-left__search--input" 
                    placeholder="Search for the location you want!" 
                    type="text"
                />
                <Btn class="flex items-center" :label="'Search'">
                    <template #icon>
                        <ArrowRightIcon height="14"/>
                    </template>
                </Btn>
            </div>
            <div class="header-left__partnership">
                <h3 class="header-left__partnership--title">
                    Our Partnership 
                </h3>
                <div class="header-left__partnership--items flex items-center">
                    <div>
                        <img src="./../assets/images/traveloka.png"/>
                    </div>
                    <div>
                        <img src="./../assets/images/airbnt.png"/>
                    </div>
                    <div>
                        <img src="./../assets/images/ticketcom.png"/>
                    </div>
                    <div>
                        <img src="./../assets/images/tripadvisor.png"/>
                    </div>
                </div>
            </div>
        </div>
        <div class="header-right">
           <div class="header-right__cards flex">
                <div class="header-right__cards--card">
                     <HeaderCard 
                        :title="'1K+ People'"
                        :description="'Successfully Getting Home'"
                    >
                        <template #avatar>
                            <div class="imgs">
                                <div class="img img__1">
                                    <img src="./../assets/images/human1.png" alt="">
                                </div>
                                <div class="img img__2">
                                    <img src="./../assets/images/human2.png" alt="">
                                </div>
                                <div class="img img__3">
                                    <img src="./../assets/images/human3.png" alt="">
                                </div>
                            </div>
                        </template>
                    </HeaderCard>
                </div>
                <div class="header-right__cards--card">
                    <HeaderCard 
                        title="56 Houses"
                        description="Sold Monthly"
                    >
                        <template #avatar>
                            <div>
                                <div>
                                    <img src="./../assets/images/hotel.png" alt="">
                                </div>
                            </div>
                        </template>
                    </HeaderCard>
                </div>
                <div class="header-right__cards--card">
                    <HeaderCard 
                        title="4K+"
                        description="People Looking for New Homes"
                    >
                        <template #avatar>
                            <div>
                                <div>
                                    <img src="./../assets/images/human4.png" alt="">
                                </div>
                            </div>
                        </template>
                    </HeaderCard>
                </div>
           </div>
        </div>
        <div class="lines"></div>
    </header>
</template>

<script>
import Btn from './Btn.vue'
import HeaderCard from './HeaderCard.vue'
export default {    
    components: {
        Btn,
        HeaderCard
    }
}
</script>