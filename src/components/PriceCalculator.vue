<template>
    <div class="container">
        <div class="table-wrapper">
            <div class="column pp">
                <div class="row">
                    <div class="row-text">PP</div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_pp">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_pp_12">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_pp_13">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_pp_14">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_pp_15">
                    </div>
                </div>
            </div>
            <div class="column mu">
                <div class="row">
                    <div class="row-text">RP</div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_retail">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_mu_1">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_mu_2">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_mu_3">
                    </div>
                </div>
                <div class="row">
                    <div class="row-box">
                        <input type="number" v-model="text_mu_4">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PriceCalculator',
    data () {
        return {
            text_pp: 0,
            text_pp_12: 0,
            text_pp_13: 0,
            text_pp_14: 0,
            text_pp_15: 0,
            text_retail: 0,
            text_mu_1: 0,
            text_mu_2: 0,
            text_mu_3: 0,
            text_mu_4: 0
        }
    },
    watch: {
        text_pp: function() {
            this.text_pp_12 = Math.floor((this.text_pp * 1.2));
            this.text_pp_13 = Math.floor((this.text_pp * 1.3));
            this.text_pp_14 = Math.floor((this.text_pp * 1.4));
            this.text_pp_15 = Math.floor((this.text_pp * 1.5));
        },
        text_retail: function() {
            this.text_mu_1 = Math.floor((this.text_retail - this.text_pp_12));
            this.text_mu_2 = Math.floor((this.text_retail - this.text_pp_13));
            this.text_mu_3 = Math.floor((this.text_retail - this.text_pp_14));
            this.text_mu_4 = Math.floor((this.text_retail - this.text_pp_15));
        },
    }
}
</script>

<style scoped>
.container {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100vh;
}
.table-wrapper {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-evenly;
    width: 100%;
    max-width: 800px;
}
.column {
    display: flex;
    flex-flow: column nowrap;
    padding: 0 10px;
}
.row {
    display: flex;
    flex-flow: row nowrap;
    justify-content: right;
    align-items: center;
    margin-bottom: 20px;
}
.row-text {
    padding: 10px;
    border-radius: 4px;
    background-color: #e4e9ee;
}
@media only screen and (max-width: 725px) {
    .column {
        width: 100%;
        max-width: 100%;
    }
    .row {
        justify-content: center;
    }
}
</style>
