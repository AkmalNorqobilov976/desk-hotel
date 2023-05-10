<template>
    <div id="Recommendation">
        <PageTitle class="recommendation-title" title="Our Recommendation"/>
        <div class="recommendation-head flex justify-space-between">
            <h3 class="recommendation-head__title">
                Featured House
            </h3>
            <div class="recommendation-head__filter-navigator flex">
                <div class="recommendation-head__filter-navigator--filter flex">
                    <Btn 
                        v-for="btn, i in fltrs" 
                        :key="i"
                        :color="'black'" 
                        :label="btn.title" 
                        :className="'row-reverse'"
                    >
                        <template #icon>
                            <component :is="btn.icon"/>
                        </template>
                    </Btn>
                </div>
                <div class="recommendation-head__filter-navigator--navigator flex items-center">
                    <Btn>
                        <template #icon>
                            <ArrowLeftIcon/>
                        </template>
                    </Btn>
                    <Btn>
                        <template #icon>
                            <ArrowRightIcon/>
                        </template>
                    </Btn>
                </div>
            </div>

        </div>

        <div class="recommendation-cards flex">
            <RecommendationCard 
                v-for="card, i in cards" 
                :key="i"
                :title="card.title"
                :description="card.description"
                :userName="card.userName"
                :address="card.address"
                :btnLabel="card.btnLabel"
                :btnBgColor="card.btnBgColor"
                :btnColor="card.btnColor"
                :icon="card.icon"
                :userImage="card.userImage"
            >
                <template #image>
                    <img :src="card.image" alt="">
                </template>

                <template #userImage>
                    <img  :src="card.userImage" alt="">
                </template>
            </RecommendationCard>
        </div>
    </div>
</template>

<script>
import Btn from './Btn.vue'
import PageTitle from './PageTitle.vue'
import RecommendationCard from './RecommendationCard.vue'
export default {
  components: { PageTitle, Btn, RecommendationCard },
  data: () => ({
    fltrs: [
        {
            icon: 'HouseIcon',
            title: 'House' 
        },
        {
            icon: 'VillaIcon',
            title: 'Villa' 
        },
        {
            icon: 'ApartmentIcon',
            title: 'Apartment' 
        }
    ],
    navigators: [
        'ArrowLeftIcon',
        'ArrowRightIcon'
    ],
    cards: [
        {
            image: require('./../assets/images/home1.png')
        },
        {
            image: require('./../assets/images/home2.png'),
            title: 'Woodlandside',
            description: '$ 20.000.000',
            userName: 'Robert Fox',
            address: 'Dr. San Jose, South Dakota',
            userImage: require('./../assets/images/human5.png'),
            btnLabel: 'New house',
            btnBgColor: '#DBEAFE',
            btnColor: '#1D4ED8',
            icon: 'HouseIcon'
        },
        {
            image: require('./../assets/images/home3.png'),
            title: 'The Old Lighthouse',
            description: '$ 44.000.000',
            userName: 'Ronald Richards',
            address: 'Santa Ana, Illinois',
            userImage: require('./../assets/images/human6.png'),
            btnLabel: 'Best Deals',
            btnBgColor: '#D1FAE5',
            btnColor: '#047857',
            icon: 'WalletIcon'
        },
        {
            image: require('./../assets/images/home4.png'),
            title: 'Cosmo\'s House',
            description: '$ 22.000.000',
            userName: 'Jenny Wilson',
            address: 'Preston Rd. Inglewood, Maine 98380',
            userImage: require('./../assets/images/human7.png'),
            btnLabel: 'Popular',
            btnBgColor: '#FEE2E2',
            btnColor: '#EF4444',
            icon: 'FireIcon'
        },
        {
            image: require('./../assets/images/home5.png'),
            title: 'Cosmo\'s House',
            description: '$ 22.000.000',
            userName: 'Jenny Wilson',
            address: 'Preston Rd. Inglewood, Maine 98380',
            userImage: require('./../assets/images/human7.png'),
            btnLabel: 'Popular',
            btnBgColor: '#FEE2E2',
            btnColor: '#EF4444',
            icon: 'FireIcon'
        }
    ]
  })
    
}
</script>