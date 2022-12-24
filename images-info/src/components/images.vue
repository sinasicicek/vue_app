<script>

export default {
    data(){return{
        click_src:null,
        img_state:"showOff",
        boy_en:"",
        info_data:false,
        img_dizi:[
       
        "../src/assets/mask.jpeg",
        "../src/assets/mask2.jpeg",
        ]
    }},
    
    created(){
        
        this.click_src=""
    },
 
    methods:{
        info_click(nesne){
            
            this.img_state="showOn"
            this.click_src=this.img_dizi[nesne.target.id]
            


                        //tıklanan resisim width  ve height degerleri çekiliyor
            const nesne_id=document.getElementById("click_img_id")
            const he=nesne_id.height

            //width ve height degeleri atanıyor
            //this.boy_en=`height:${he}px`
            console.log(he);
        },
        kapat(){
            this.img_state="showOff"
            const ekle=document.getElementById("info-data")
            ekle.innerHTML=""
            this.boy_en=null
        },
    
        
            
            
    }
}

</script>
<template>
    <div class="contain d-flex d-flex-center d-flex-col">
        
        <div class="contain-upload d-flex ">
            <nav>
        <ul>
            <li>Vector</li>
            <li>Illustrations</li>
            <li>Images</li>
            <li>Icons</li>
        </ul>
        </nav>
            <div class="contain-upload-item">
                <input type="text" class="contain-upload-input" placeholder="Search">
                <button class="contain-upload-btn">Upload</button></div>
        </div>
        <hr class="contain-upload-br"/>
        <div class="contain-img" >
       
            <img :src="img_dizi[index]" alt="" @click="info_click($event)" v-for="(item,index) in 30" :id="index">
            
           
        </div>

    </div>
    <div class=" showOn-click" :class="img_state">
        <div class="show-on-click-div"><button class="img-x" @click="kapat">X</button></div>
        <div class="show-img-contain">
            <img class="show-img" :class="img_state"  :src="click_src" alt="" id="click_img_id">
            <div class="show-img-info" :style="boy_en">
                <div id="info-data"></div>
            </div>
        </div>
        </div>
</template>
<style>
#info-data{
    width: 100%;
    height: 100%;
}
.inf-ul{
    display: flex;
    flex-direction: column;
}
.img-x{
    width: 40px;
    height: 40px;
    position: relative;
  
    
    margin:1rem 0rem;
    border-radius: 50%;
}
.img-x:hover{
    cursor: pointer;
    border-color: rebeccapurple;
}
.showOff{
    display: none;
    visibility: hidden;
}
.showOn{
    display: block;
}

.showOn-click{
   /* width: 100%;
    max-width: 1200px;*/
    height: 100%;
    z-index: 12;
    position: fixed;
   top: 1%;
    left: 1%;
    right: 1%;
    
}
.show-on-click-div{
    display: flex;
    justify-content: flex-end;
   
}
.show-img-contain{
    display: flex;
    max-width: 100%;
    max-height: 600px;
    justify-content: center;
    align-items: center;
}
.show-img{
    width: 20%;
    height:400px;
    
}

.show-img-info{
   width: 30%;
    height: 400px;
    background-color: #334043;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    color: white;
    
}
.show-img-info > p {
    max-width: 100%;
   
    font-size: 18px;
}
nav{
    width: 100%;
    display: flex;
    align-items: center;
    
}
li:hover{
    cursor: pointer;
    border-bottom: 1px solid #334043;
    transition: 1s;
}
.contain-img{
   
    width: 100%;
    height: 50%;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
}
.contain-img > img{

 padding: 1rem;
    width: 350px;
    height: 300px;
    opacity: 0.5;
}
.contain-img > img:hover{cursor: pointer; opacity: 1;}
.contain{
    width: 60%;
    
    justify-content:space-evenly;
    background-color: white;
    padding: 3rem;
    position: relative;
   
   
}
.contain-upload-br{
    content: "";
    display: block;
    width: 100%;
    height: 2px;
    background-color: #334043;
}
.contain-upload{
    width: 100%;
   margin-bottom: 3rem;
    align-items: center;
    justify-content: center;
}
.contain-upload-item{width: 100%; align-items: center;display: flex;
    justify-content: end;}
.contain-upload-input{
    border: 0px;
    border-bottom: 1px solid #334043;
    
}
.contain-upload-input:focus{
    
    
    outline-offset: 0px;
    outline: none;
}
.contain-upload-btn{
    width: 150px;
    padding: .4rem;
    font-size: 18px;
    background-color: #334043;
    color: white;
    border: 0px;
    border-radius: 3px;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    margin-left: 20px;
}
.contain-upload-btn:hover{
    cursor: pointer;
}
.contain-upload-btn:active{transform: scale(.7);}
</style>