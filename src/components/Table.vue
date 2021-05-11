<template>
    <div>
        <table>
            <tr>
                <td class="co1" @click.once="giveSymbol(0,$event)" id="btn1"></td>
                <td class="co2" @click.once="giveSymbol(1,$event)" id="btn2"></td>
                <td class="co1" @click.once="giveSymbol(2,$event)" id="btn3"></td>
            </tr>
            <tr>
                <td class="co2" @click.once="giveSymbol(3,$event)" id="btn4"></td>
                <td class="co1" @click.once="giveSymbol(4,$event)" id="btn5"></td>
                <td class="co2" @click.once="giveSymbol(5,$event)" id="btn6"></td>
            </tr>
            <tr>
                <td class="co1" @click.once="giveSymbol(6,$event)" id="btn7"></td>
                <td class="co2" @click.once="giveSymbol(7,$event)" id="btn8"></td>
                <td class="co1" @click.once="giveSymbol(8,$event)" id="btn9"></td>
            </tr>
        </table>
    </div>
</template>

<script type="text/javascript">
export default {
    data() {
        return {
            firster: {
                name: "firster",
                value: "○",
                markplace: "○です"
            },
            seconder: {
                name: "seconder",
                value: "×",
                markplace: "×です"
            },
            states: [
                // [0,1,2],
                // [0,4,8],
                // [0,3,6],
                // [3,4,5],
                // [6,7,8],
                // [1,4,7],
                // [2,5,8],
                // [2,4,6]
                0,1,2,3,4,5,6,7,8,
            ],
            count: 0,
            playerCount:0
        }
    },
    methods: {
        giveSymbol: function(number,event){
            let id = event.target.id;
            let selectBtn = document.getElementById(id);
            this.count++;
            this.playerCount++; 
            if(this.count % 2 != 0){
                selectBtn.innerHTML = this.firster.value;
                this.states[number] = this.firster.value;
                this.judgement();
            } else {   
                selectBtn.innerHTML = this.seconder.value;
                this.states[number] = this.seconder.value;
            }
            
        },
        judgement: function(){
            if(this.states[0] == this.states[1] && this.states[1] == this.states[2]){
                this.whichWin();
            }
        },
        whichWin: function(){
            if(this.playerCount / 2 != 0){
                alert(this.firster.name);
            } else {
                alert(this.seconder.name)
            }
        }

    }
}
</script>

<style scoped>
table{
    text-align: center;
    margin: 0 auto;
    border-collapse: collapse;
}
td{
    width: 100px;
    height: 100px;
    font-size: 70px;
}
.co1{
    background-color: cadetblue;
}
.co2{
    background-color: darkgrey;
}
</style>