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
        <p v-if="this.firster.gameresult">The winner of this game is {{this.firster.name}} .</p>
        <p v-if="this.seconder.gameresult">The winner of this game is {{this.seconder.name}} .</p>
        <p v-if="this.gameover">The game is draw</p>
    </div>
</template>

<script type="text/javascript">
export default {
    data() {
        return {
            firster: {
                name: "firster",
                value: "○",
                gameresult:false
            },
            seconder: {
                name: "seconder",
                value: "×",
                gameresult:false
            },
            states: [0,1,2,3,4,5,6,7,8],
            count: 0,
            gameover:false,
            btnMove:false,
        }
    },
    methods: {
        giveSymbol: function(number,event){
            let id = event.target.id;
            let selectBtn = document.getElementById(id);
            this.count++;
            if(this.count % 2 != 0){
                selectBtn.innerHTML = this.firster.value;
                this.states[number] = this.firster.value;
                this.judgement();
            } else {   
                selectBtn.innerHTML = this.seconder.value;
                this.states[number] = this.seconder.value;
                this.judgement();
            }
        },
        judgement: function(){
            if(this.states[0] == this.states[1] && this.states[1] == this.states[2]){
                this.whichWin();
            } else if(this.states[0] == this.states[4] && this.states[4] == this.states[8]) {
                this.whichWin();
            } else if(this.states[0] == this.states[3] && this.states[3] == this.states[6]){
                this.whichWin();
            } else if(this.states[1] == this.states[4] && this.states[4] == this.states[7]){
                this.whichWin();
            } else if(this.states[2] == this.states[5] && this.states[5] == this.states[8]){
                this.whichWin();
            } else if(this.states[3] == this.states[4] && this.states[4] == this.states[5]){
                this.whichWin();
            } else if(this.states[6] == this.states[7] && this.states[7] == this.states[8]){
                this.whichWin();
            } else if(this.states[2] == this.states[4] && this.states[4] == this.states[6]){
                this.whichWin();
            } else if(this.count == 9){
                this.gameover = true
            }
        },
        whichWin: function(){
            if(this.count % 2 != 0){
                this.firster.gameresult = true
            } else {
                this.seconder.gameresult = true
            }
        },
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