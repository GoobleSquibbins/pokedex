<template>
    <div>
        <h1 class="text-[50px] text-center">Diskon</h1>
        <div class="main flex flex-col items-center w-full">
            <div class="daform flex flex-col items-center justify-center m-auto w-[100%]">
                <form @submit.prevent="idkmanplswork">
                    <label class=" font-medium ">Total Pembelian</label>
                    <br>
                    <input type="number" required v-model="totalHarga" class="rounded border-[1px] border-black w-[200px]">
                    <br>
                    <br>
                    <button class="border-[1px] border-black p-[2px] w-[200px] rounded">Submit</button>
                </form>
            </div>
            <div class="out flex flex-col items-start mt-[10px]" v-if="x == ''">
                <table>
                    <tr>
                        <td>Total Pembelian</td>
                        <td> : </td>
                        <td>{{ totalHarga }}</td>
                    </tr>
                    <tr>
                        <td>Diskon</td>
                        <td> : </td>
                        <td>{{ diskon }}</td>
                    </tr>
                    <tr>
                        <td>Harga Final</td>
                        <td> : </td>
                        <td>{{ abisKenaDiskon }}</td>
                    </tr>
                </table>
            </div>
            <div class="out2">
                <p>{{ x }}</p>
            </div>
        </div>
    <!-- <p></p> -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            totalHarga: '',
            abisKenaDiskon: '',
            diskon: '',
            x: '',
        }
    },
    methods: {
        idkmanplswork() {
            if (this.totalHarga >= 100000) {
                this.diskon = '10%'
                this.abisKenaDiskon = this.totalHarga - (this.totalHarga * 0.1)
            }

            if (this.totalHarga >= 50000 && this.totalHarga < 100000) {
                this.diskon = '5%'
                this.abisKenaDiskon = this.totalHarga - (this.totalHarga * 0.05)
            }

            if (this.totalHarga < 50000) {
                this.diskon = 'Tidak ada diskon'
                this.abisKenaDiskon = this.totalHarga
            }

            if (this.totalHarga < 0) {
                this.x = 'Invalid Input'
            }

        }
    }
}
</script>

<style lang="scss" scoped></style>