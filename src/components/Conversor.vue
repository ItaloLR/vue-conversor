<template>
    <div class="conversor">
        <h2>{{moedaA}} To {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" :placeholder="moedaA">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>
export default {
    name: "Conversor",
    props: ["moedaA","moedaB"],
        data() {
            return {
                moedaA_value: "",
                moedaB_value: 0
            };
        },
    methods: {
        converter() {
            let de_para = this.moedaA + "_" + this.moedaB;

            const apiKey = "2fbeba68a182fcb129c7";
        
            let url = "https://free.currconv.com/api/v7/convert?q="+ de_para
            +"&compact=y&apiKey=" + apiKey;

            fetch(url).then(res => {
                return res.json();
                })
                    .then(json => {
                            let cotacao = json[de_para].val;
                            this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                        });
        }
    }
    
};
</script>

<style scoped>

.conversor {
    background-color: #fff;
    max-width: 300px;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

input[type=button] {
    margin-left: 5px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    height: 21px;
    color: #fff;
    font-weight: bold;
    text-align: center;
    background-color: #4297bd;
}

</style>