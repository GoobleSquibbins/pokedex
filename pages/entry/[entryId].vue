<template>
    <div>
        <NuxtLink to="/">
            <button class="m-[45px] p-[20px] bg-[#21628D] text-white w-[200px] rounded-lg shadow-2xl absolute hover:bg-[#2D81B9] transition ease-in-out delay-[30ms]">
                Back to Home page
            </button>
        </NuxtLink>

        <div class="w-full h-full flex flex-col items-center justify-center" v-for="entryy in data.filter(
            function (i) { return i.entry == entryId })">
            <div class="w-[100%] flex flex-col items-center">
                <div class="header border-b-[1px] border-black text-center mb-[30px] ">
                    <h1 class="text-[5rem] font-medium">{{ entryy.name }}</h1>
                    <p>{{ entryy.flavourText }}</p>
                </div>

                <div class="overview w-full grid grid-cols-4 gap-4">
                    <div class="img m-[20px] col-span-1 flex flex-row items-center justify-center">
                        <img width="350px" :src="entryy.detailedSprite" alt="">
                    </div>
                    <div class="stats col-span-3 grid grid-cols-3 gap-2">
                        <div class="pokedexData flex flex-col items-center">
                            <h1 class="text-[2rem] font-medium text-center">Pokédex Data</h1>
                            <table>
                                <tr>
                                    <td class="text-end text-[#636363]">National Dex No.</td>
                                    <td>{{ entryy.entry }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">
                                        <p>Type</p>
                                    </td>
                                    <td>
                                        <div class="flex flex-row items-center justify-start">
                                            <img class="mr-[10px]" :src="entryy.type" alt="">
                                            <img :src="entryy.type2" alt="">
                                        </div>
                                    </td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Species</td>
                                    <td>{{ entryy.detailStats[0].pokedexData[0].species }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Height</td>
                                    <td>{{ entryy.detailStats[0].pokedexData[0].height }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Weight</td>
                                    <td>{{ entryy.detailStats[0].pokedexData[0].weight }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Abilites</td>
                                    <td>
                                        <ul>
                                            <li class="text-[12px]"
                                                v-for="ability in entryy.detailStats[0].pokedexData[0].abilities">{{ ability
                                                }}</li>
                                        </ul>
                                    </td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Local No.</td>
                                    <td>{{ entryy.detailStats[0].pokedexData[0].localNo }}</td>
                                </tr>
                            </table>
                        </div>
                        <div class="training flex flex-col items-center">
                            <h1 class="text-[2rem] font-medium text-center">Training</h1>
                            <table>
                                <tr>
                                    <td class="text-end text-[#636363]">EV Yield</td>
                                    <td>{{ entryy.detailStats[0].trainingData[0].evYield }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Catch Rate</td>
                                    <td>{{ entryy.detailStats[0].trainingData[0].catchRate }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Base Friendship</td>
                                    <td>{{ entryy.detailStats[0].trainingData[0].baseFriendship }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Base Exp</td>
                                    <td>{{ entryy.detailStats[0].trainingData[0].baseExp }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Growth Rate</td>
                                    <td>{{ entryy.detailStats[0].trainingData[0].growthRate }}</td>
                                </tr>
                            </table>
                        </div>
                        <div class="breeding flex flex-col items-center">
                            <h1 class="text-[2rem] font-medium text-center">Breeding</h1>
                            <table>
                                <tr>
                                    <td class="text-end text-[#636363]">Egg Groups</td>
                                    <td>{{ entryy.detailStats[0].breedingData[0].eggGroup }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Gender</td>
                                    <td>
                                        <span class="text-[#5C93EC] mr-[5px]">{{
                                            entryy.detailStats[0].breedingData[0].genderMale }}</span>
                                        <span class="text-[#EC5DA1]">{{ entryy.detailStats[0].breedingData[0].genderFemale
                                        }}</span>
                                    </td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Egg Cycles</td>
                                    <td>{{ entryy.detailStats[0].breedingData[0].eggCycle }}</td>
                                </tr>
                            </table>
                        </div>
                        <div class="baseStats flex flex-col items-center">
                            <h1 class="text-[2rem] font-medium text-center">Base Stats</h1>
                            <table>
                                <tr>
                                    <td class="text-end text-[#636363]">HP</td>
                                    <td>{{ entryy.baseStats[0].hp }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Attack</td>
                                    <td>{{ entryy.baseStats[0].att }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Defense</td>
                                    <td>{{ entryy.baseStats[0].def }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Sp.Atk</td>
                                    <td>{{ entryy.baseStats[0].spa }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Sp.Def</td>
                                    <td>{{ entryy.baseStats[0].spdf }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Speed</td>
                                    <td>{{ entryy.baseStats[0].spd }}</td>
                                </tr>
                                <tr>
                                    <td class="text-end text-[#636363]">Total</td>
                                    <td>{{ entryy.baseStats[0].total }}</td>
                                </tr>
                            </table>
                        </div>
                        <div class="typeDefense flex flex-col items-center col-span-2">
                            <h1 class="text-[2rem] font-medium text-center">Type Defense</h1>
                            <table>
                                <tr>
                                    <td>Normal</td>
                                    <td>Fire</td>
                                    <td>Water</td>
                                    <td>Electric</td>
                                    <td>Grass</td>
                                    <td>Ice</td>
                                    <td>Fighting</td>
                                    <td>Poison</td>
                                    <td>Ground</td>
                                </tr>
                                <tr>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].normal }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].fire }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].water }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].electric }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].grass }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].ice }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].fighting }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].poison }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].ground }}</td>
                                </tr>
                                <tr>
                                    <td>Flying</td>
                                    <td>Psychic</td>
                                    <td>Bug</td>
                                    <td>Rock</td>
                                    <td>Ghost</td>
                                    <td>Dragon</td>
                                    <td>Dark</td>
                                    <td>Steel</td>
                                    <td>Fairy</td>
                                </tr>
                                <tr>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].flying }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].psychic }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].bug }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].rock }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].ghost }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].dragon }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].dark }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].steel }}</td>
                                    <td>{{ entryy.detailStats[0].typeDefense[0].fairy }}</td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
                <div class="evolutionLine w-full m-[50px]">
                    <h1 class="text-[20px] font-medium border-b-[1px] border-black m-[20px] text-center">Evolution Line</h1>
                    <div class="w-full grid grid-cols-5 justify-center">
                        <NuxtLink :to="'/entry/' + entryy.detailStats[0].evolutionData[0].evoDex[0]">
                            <div class="first flex flex-col items-center justify-end">
                                <img width="100px" height="100px" :src="entryy.detailStats[0].evolutionData[0].evoSprite[0]"
                                    alt="">
                                <p>{{ entryy.detailStats[0].evolutionData[0].evoLine[0] }}</p>
                                <p class="text-[#939393]">#{{ entryy.detailStats[0].evolutionData[0].evoDex[0] }}</p>
                            </div>
                        </NuxtLink>

                        <div class="arrow01 w-full first flex flex-col items-center justify-center">
                            <p>===( level {{ entryy.detailStats[0].evolutionData[0].levelEvo[0] }} )==></p>
                        </div>

                        <NuxtLink :to="'/entry/' + entryy.detailStats[0].evolutionData[0].evoDex[1]">
                            <div class="second w-full first flex flex-col items-center justify-end">
                                <img width="100px" height="100px" :src="entryy.detailStats[0].evolutionData[0].evoSprite[1]"
                                    alt="">
                                <p>{{ entryy.detailStats[0].evolutionData[0].evoLine[1] }}</p>
                                <p class="text-[#939393]">#{{ entryy.detailStats[0].evolutionData[0].evoDex[1] }}</p>
                            </div>
                        </NuxtLink>

                        <div class="arrow02 w-full first flex flex-col items-center justify-center">
                            <p>===( level {{ entryy.detailStats[0].evolutionData[0].levelEvo[1] }} )==></p>
                        </div>

                        <NuxtLink :to="'/entry/' + entryy.detailStats[0].evolutionData[0].evoDex[2]">
                            <div class="final w-full h-full flex flex-col items-center justify-end">
                                <img width="100px" height="100px" :src="entryy.detailStats[0].evolutionData[0].evoSprite[2]"
                                    alt="">
                                <p>{{ entryy.detailStats[0].evolutionData[0].evoLine[2] }}</p>
                                <p class="text-[#939393]">#{{ entryy.detailStats[0].evolutionData[0].evoDex[2] }}</p>
                            </div>
                        </NuxtLink>

                    </div>
                </div>
                <div class="switchpages w-full flex flex-row items-center justify-center">
                    <div class="mr-auto m-[30px]" v-for="prevEntry in data.filter(
                        function (i) { return i.entry == prevEntry(entryy.entry) })">
                        <NuxtLink :to="'/entry/'+prevEntry.entry">
                            <button class="bg-[#21628D] p-[20px] rounded-lg shadow-lg text-white w-[170px] hover:bg-[#2D81B9] transition ease-in-out delay-[30ms]">
                                #{{ prevEntry.entry }} {{ prevEntry.name }}
                            </button>
                        </NuxtLink>
                    </div>

                    <div class="ml-auto m-[30px]" v-for="nextEntry in data.filter(
                        function (i) { return i.entry == nextEntry(entryy.entry) })">
                        <NuxtLink :to="'/entry/'+nextEntry.entry">
                            <button class="bg-[#21628D] p-[20px] rounded-lg shadow-lg text-white w-[170px] hover:bg-[#2D81B9] transition ease-in-out delay-[30ms]">
                                #{{ nextEntry.entry }} {{ nextEntry.name }}
                            </button>
                        </NuxtLink>
                    </div>

                </div>
            </div>

        </div>

    </div>
</template>

<script setup>
const { entryId } = useRoute().params
</script>

<script>
import bunchOfData from '/JASOOONN/bunchOfData.json'
export default {
    data() {
        return {
            data: bunchOfData.pokemon,
            reload: true,
            x: 0
        }
    }, methods: {
        plsreload() {
            if (this.reload) {
                this.$nuxt.refresh()
                this.reload == !this.reload
            }
        },
        prevEntry(entryNo) {
            return entryNo - 1
        },
        nextEntry(entryNo) {
            return entryNo + 1
        }
    }, beforeMount() {
        this.plsreload()
    }
}
</script>

<style scoped>
td {
    padding: 5px;
}

.typeDefense td {
    padding: 5px;
    text-align: center;
}

tr {
    border-bottom: solid #e5e5e5 1px;
    border-top: solid #e5e5e5 1px;
}
</style>