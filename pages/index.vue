<template>
    <div>
        <h1 class="text-[5rem] font-medium text-center">Pokédex</h1>
        <h3 class="text-[3rem] border-b-[1px] border-black m-[20px] text-center">Gen 5</h3>

        <div class=" grid grid-cols-4 gap-4">
            <div class="flex flex-col items-center" v-for="item in data" :key="item.entry">
                <div
                    class="m-[10px] w-[250px] h-[350px] bg-white rounded-lg drop-shadow-2xl border-[1px] border-black flex flex-col items-center p-[5px]">
                    <img :src="item.sprite">
                    <h1 class="text-[20px] font-medium text-center mt-[5px]">{{ item.name }}</h1>
                    <p>#{{ item.entry }}</p>
                    <div class="flex items-center">
                        <img class="mr-[3px]" :src="item.type" alt="">
                        <img :src="item.type2" alt="">
                    </div>
                    <p class="text-[13px] text-center mt-[7px]">{{ item.desc }}</p>
                    <p class="border-b-[1px] border-black">Base Stats</p>
                    <table class="text-[12px]">
                        <tr class="font-medium">
                            <td>Hp</td>
                            <td>Att</td>
                            <td>Def</td>
                            <td>S.Att</td>
                            <td>S.Def</td>
                            <td>Spd</td>
                        </tr>
                        <tr>
                            <td>{{ item.baseStats[0].hp }}</td>
                            <td>{{ item.baseStats[0].att }}</td>
                            <td>{{ item.baseStats[0].def }}</td>
                            <td>{{ item.baseStats[0].spa }}</td>
                            <td>{{ item.baseStats[0].spdf }}</td>
                            <td>{{ item.baseStats[0].spd }}</td>
                        </tr>
                    </table>
                </div>
            </div>

        </div>
        <footer>
            <div class="text-center bg-gray-400 font-medium p-[10px] mt-[50px]">
                <p>Copyright Arsya MMXXIII</p>
            </div>
        </footer>
    </div>
</template>

<script>
import bunchOfData from '/JASOOONN/bunchOfData.json'
export default {
    data() {
        return {
            data: bunchOfData.pokemon
        }
    }
}
</script>

<style scoped>
td {
    padding: 5px;
    text-align: center;
}

tr:last-child {
    border: 0;
}
</style>