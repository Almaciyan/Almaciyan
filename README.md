<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="Author" content="Abolfazl Almaciyan" />
    <title>Doz 24</title>
    <script type="module" src="https://unpkg.com/ionicons@7.1.0/dist/ionicons/ionicons.esm.js"></script>
<script nomodule src="https://unpkg.com/ionicons@7.1.0/dist/ionicons/ionicons.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        .container {
            width: 100%;
            height: 100vh;
            background-color: rgb(55, 122, 55);
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
        }

        .loader {
            position: fixed;
            background-color: #121212;
            width: 100%;
            height: 100%;
            z-index: 100;
        }

        .loader .d1{color: red;}
        .loader .d2{color: #01ff45;}
        .loader .d3{color: rgb(0, 51, 255);}
        .loader .d4{color: #f700ff;}
        .loader .d5{color: rgb(255, 204, 0);}
        .loader .d6{color: #00ffcc}
        .loader .d7{color: #ff4501;}
        .orbit { 
            width: 150px;
            height: 150px;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            color: #fff;
            font-size: 2em;
            font-weight: 800;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            text-shadow: 0 0 20px rgb(67, 67, 87);
        }

        .orbit::after {
            content: '';
            position: absolute;
            width: calc(100% + 18px);
            height: calc(100% + 18px);
            border-radius: 50%;
            border: 4px solid #0d0065;
            border-bottom: 4px solid #ffffff ;
            border-left: 4px solid rgb(255, 255, 255) ;
            animation: charkho 4s ease-in-out infinite;
        }
        
        .orbit .ord {
            position: absolute;
            width: 50%;
            left: 50%;
            height: 4px;
            transform-origin: left;
            animation: charkh 4s ease-in-out infinite;
        }
        .orbit .ord::after {
            content: '';
            position: absolute;
            width: 30px;
            height: 30px;
            background-color: #0d0065;
            left: calc(100% - 10px);
            border-radius: 50%;
        }

        .orbit ::after {
            content: '';
            position: absolute;
            box-shadow: 0 0 30px 5px rgba(0, 0, 230, .4);
        }

        @keyframes charkho {
            0%{
                transform: rotate(-45deg);
            }
            100%{
                transform: rotate(315deg);
            }
        }

        @keyframes charkh {
            0%{
                transform: rotate(-13deg);
            }
            100%{
                transform: rotate(347deg);
            }
        }

        .mymenu {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            transition: .5s;
            z-index: 2;
        }

        .mymenu:hover {
            height: 40px;
        }

        .mymenu span {
            color: #fff;
            font-size: 2.2em;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            margin-top: 5px;
        }

        .page , .dozpage, .option {
            width: 100vw;
            height: 98vh;
            backdrop-filter: blur(30px);
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            display: grid;  
        }

        .dozpage {
            display: none;
        }

        .page {
            z-index: 3;
            justify-content: center;
            align-items: center;
            justify-items: center;
            border-radius: 20px;
        }

        .page div {
            background-color: rgba(255, 255, 255, 0.7);
            padding: 2px 8px;
            border-radius: 15px;
            position: relative;
            font-size: 2em;
            cursor: pointer;
            border-top: 2px solid rgba(255, 255, 255, 0.4);
            border-left: 2px solid rgba(255, 255, 255, 0.4);
            border-right: 2px solid rgba(255, 255, 255, 0.4);
            border-bottom: 2px solid rgba(255, 255, 255, 0.4);
        }


        .page div:hover {
            transform: scale(1.2);
        }
        
        .option {
            display: none;
            z-index: 5;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .option h3 {
            position: absolute;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            width: 100%;
            height: 30px;
            font-weight: 300;
            margin-top: 1px;
            user-select: none;
        }

        .option picture {
            position: absolute;
            width: 100%;
            height: 50%;
            display: grid;
            grid-template-columns: repeat(3, 33.3333333%);
            justify-content: center;
            justify-items: center;
            align-items: center;
            grid-gap: 5px;
            margin: auto 3px;
            margin-top: 20px;
            overflow: hidden;
            padding: 8px;
        }

        .option img {
            display: grid;
            max-width: 90%;
            height: 90%;
            justify-content: center;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 5px;
            cursor: pointer;
        }

        .colorm {
            color: #fff;
            width: 100%;
            height: 39%;
            display: grid;
            justify-content: center;
            position: absolute;
            margin-top: calc(50% + 10%);
            grid-template-rows: 20% repeat(2, 30%) ;
            grid-template-columns: repeat(4, 25%);
        }

        .colorm span {
            grid-column: 1/-1;
            justify-self: center;
            user-select: none;
        }
        .colorm span:last-child {
        user-select: auto;
        cursor: pointer
        ;}

        .noma1, .noma2 {
            margin-left: 10px;
            grid-column: 1/2;
            user-select: none;
        }

        .colorm .colorb, .colorm .colorr {
            width: 100%;
            grid-column: 1/-1;
            display: grid;
            grid-template-columns: repeat(4, 25%);
            justify-items: center;
            align-items: center;
        }

        .colorm .color {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
        }

        .colorm .color.active {    
            border: 2px solid #ffff;
            outline: 1px solid #000;
        }
        
        .color.co1 {background-color: black;}
        .color.co2 {background-color: rgb(0, 0, 106);}
        .color.co3 {background-color: rgb(14, 42, 3);}
        .color.co4 {background-color: red;}
        .color.co5 {background-color: rgb(0, 238, 255);}
        .color.co6 {background-color: rgb(211, 255, 54);}

        .line {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            display: grid;
            grid-template-columns: repeat(3, 33.333333%);
            grid-template-rows: repeat(3, 33.3333333%);
            user-select: none;
        }
        
        .line.l1 {
            width: 98%;
            height: 98%;
        }

        .line.l2 {
            width: 70%;
            height: 70%;
        }

        .line.l3 {
            width: 42%;
            height: 42%;
        }

        .line .circles {
            background-color: #fff;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            z-index: 1;
            transform: scale(1);
        }

        .circles {
            margin: 3px;
            display: grid;
            justify-items: center;
            align-items: center;
        }

        .dozpage .circles.c2, 
        .dozpage .circles.c8 {
            justify-self: center;
        }
        .dozpage .circles.c3, 
        .dozpage .circles.c6, 
        .dozpage .circles.c9 {
            justify-self: end;
        }

        .dozpage .circles.c4,
        .dozpage .circles.c6 {
            align-self: center;
        }

        .dozpage .circles.c7, 
        .dozpage .circles.c8, 
        .dozpage .circles.c9 {
            align-self: end;
        }
        
        .inline {
            background-color: #fff;
            position: absolute;
        }

        .inline.l1 {
            height: 5px;
            width: calc(99% - 10px);
            justify-self: center;
            margin-top: 15.5px;
        }

        .inline.l2 {
            height: calc(99% - 10px);
            left: 10px;
            width: 5px;
            align-self: center;
            margin-left: 15.5px;
        }

        .inline.l3 {
            right: 10px;
            height: calc(99% - 10px);
            width: 5px;
            align-self: center;
            margin-right:  15.5px;
        }

        .inline.l4 {
            height: 5px;
            bottom: 10px;
            width: calc(99% - 10px);
            justify-self: center;
            margin-bottom: 15.5px;
        }

        .inline.ld1 {
            height: 5px;
            width: 44%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(45deg);
            transform-origin: left;
            top: 13px;
            left: 15px;
        }

        .inline.ld2 {
            height: 5px;
            width: 30%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(90deg);
            transform-origin: left;
            top: 13px;
            left: 50%;
        }

        .inline.ld3 {
            height: 5px;
            width: 44%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(-45deg);
            transform-origin: right;
            top: 13px;
            right: 15px;
        }

        .inline.ld4 {
            height: 5px;
            bottom: 10px;
            width: 30%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(0);
            transform-origin: left;
            top: 50%;
            left: 15px;
        }

        .inline.ld5 {
            height: 5px;
            bottom: 10px;
            width: 30%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(0deg);
            transform-origin: left;
            top: 50%;
            right: 15px;
        }

        .inline.ld6 {
            height: 5px;
            bottom: 10px;
            width: 43%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(-45deg);
            transform-origin: left;
            bottom: 0px;
            left: 15px;
        }
        .inline.ld7 {
            height: 5px;
            bottom: 10px;
            width: 30%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(-90deg);
            transform-origin: left;
            bottom: 0px;
            left: 50%;
        }
        .inline.ld8 {
            height: 5px;
            width: 43%;
            justify-self: center;
            margin-bottom: 15.5px;
            transform: rotate(45deg);
            transform-origin: right;
            bottom: 0px;
            right: 18px;
        }
        .circles.c5{visibility: hidden;}

        @media only screen and (max-width : 470px) {
            .line .circles {
                width: 25px;
                height: 25px;
            }
            .inline.l3 {
                margin-top: 5px;
            }
            .inline.l2 {
                margin-left: 5px;
            }
            .inline.l3 {
                margin-right: 5px;
            }
            .inline.l4 {
                margin-bottom: 5px;
            }
        }

        @media only screen and (max-height : 470px) {
            .line .circles {
                width: 25px;
                height: 25px;
            }
            .inline.l3 {
                margin-top: 5px;
            }
            .inline.l2 {
                margin-left: 5px;
            }
            .inline.l3 {
                margin-right: 5px;
            }
            .inline.l4 {
                margin-bottom: 5px;
            }
        }
        .circles.dop {
            animation:dop .3s infinite ease-in-out;
        }
        @keyframes dop {
            0%{
                transform: scale(1.2);
            }
            100%{
                transform: scale(1);
            }
        }

        .message {
            display: none;
            background-color: #fff;
            z-index: 10;
            width: 80%;
            height: max-content;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 10px;
            text-align: center;
            border-radius: 10px;
            border: 3px solid rgba(0, 0, 0, .3);
        }
        .message .yes {
            color: #000;
            font-size: 1.2em;
            float: right;
            width: 48%;
            border-bottom: 2px solid rgba(0, 0, 0, .3);
            margin-top: 10px;
        }

        .message .no {
            color: #000;
            font-size: 1.2em; 
            width: 48%;
            border-bottom: 2px solid rgba(0, 0, 0, .3);
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="loader">
            <div class="orbit"><span class="d1">L</span><span class="d2">o</span><span class="d3">a</span><span class="d4">d</span><span class="d5">i</span><span class="d6">n</span><span class="d7">g</span>
                <span class="ord"></span>
            </div>
        </div>
        <div class="message">
            <h3> برای تغییر تنظیمات بازی شما از اول اجرا خواهد شد قبول می کنید</h3>
            <div class="yes">قبول می کنم</div>
            <div class="no"> لغو</div>
        </div>
        <div class="mymenu">
            <span><ion-icon name="home"></ion-icon></span>
        </div>
        <div class="page">
            <div class="start">شروع</div>
            <div class="restart">بازی مجدد</div>
            <div class="about">تنظیمات</div>
            <div class="about">درباره</div>
        </div>
        <div class="option">
            <h3>تصویر پس زمینه</h3>
            <picture>
                <img src=https://s31.picofile.com/file/8468775242/WallpaperGram_IR_1562149262_z18163.jpg">
                <img src="https://s30.picofile.com/file/8468987350/WallpaperGram_IR_1561887212_z49360.jpg">    
                <img src="https://s31.picofile.com/file/8467765418/background3.png">    
            </picture>
            <div class="colorm"> <span>رنگ مهره ها</span>
                <div class="colorb">
                    <div class="noma1">مهره ی اول</div>
                    <div class="color active co1"></div>
                    <div class="color co2"></div>
                    <div class="color co3"></div>
                </div>
                <div class="colorr">
                    <div class="noma2">مهره ی دوم</div>
                    <div class="color active co4"></div>
                    <div class="color co5"></div>
                    <div class="color co6"></div>
                </div>
                <span id="tayid"> تایید </span>
            </div>
        </div>

        </div>
        <div id="dozpage" class="dozpage">
            <div class="line l1">
                <div class="circles 11 a1"></div>
                <div class="circles c2 a2"></div>
                <div class="circles c3 a3"></div>
                <div class="circles c4 a4"></div>
                <div class="circles c5 a5"></div>
                <div class="circles c6 a6"></div>
                <div class="circles c7 a7"></div>
                <div class="circles c8 a8"></div>
                <div class="circles c9 a9"></div>
                <div class="inline l1"></div>
                <div class="inline l2"></div>
                <div class="inline l3"></div>
                <div class="inline l4"></div>
                <div class="inline ld1"></div>
                <div class="inline ld2"></div>
                <div class="inline ld3"></div>
                <div class="inline ld4"></div>
                <div class="inline ld5"></div>
                <div class="inline ld6"></div>
                <div class="inline ld7"></div>
                <div class="inline ld8"></div>
            </div>
            <div class="line l2">
                <div class="circles c1 b1"></div>
                <div class="circles c2 b2"></div>
                <div class="circles c3 b3"></div>
                <div class="circles c4 b4"></div>
                <div class="circles c5 b5"></div>
                <div class="circles c6 b6"></div>
                <div class="circles c7 b7"></div>
                <div class="circles c8 b8"></div>
                <div class="circles c9 b9"></div>
                <div class="inline l1"></div>
                <div class="inline l2"></div>
                <div class="inline l3"></div>
                <div class="inline l4"></div>
            </div>
            <div class="line l3">
                <div class="circles c1 d1"></div>
                <div class="circles c2 d2"></div>
                <div class="circles c3 d3"></div>
                <div class="circles c4 d4"></div>
                <div class="circles c5 d5"></div>
                <div class="circles c6 d6"></div>
                <div class="circles c7 d7"></div>
                <div class="circles c8 d8"></div>
                <div class="circles c9 d9"></div>
                <div class="inline l1"></div>
                <div class="inline l2"></div>
                <div class="inline l3"></div>
                <div class="inline l4"></div>
        </div>
        <audio src="https://.jeebstore.com/2020/03/1-1.mp3"></audio>
        <audio src="https://soundsnap-prod.nyc3.digitaloceanspaces.com/files/audio/pj/transcode/479401-Knight_Capturing_A_Pawn_03.mp3?response-content-disposition=attachment%3B+filename%3D%22479401-Knight_Capturing_A_Pawn_03.mp3%22&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AD4PI63EK5AJWZMJZZKH%2F20231106%2Fnyc3%2Fs3%2Faws4_request&X-Amz-Date=20231106T132132Z&X-Amz-SignedHeaders=host&X-Amz-Expires=30&X-Amz-Signature=e5f0592530ad8e5274312a96ee00000080edbee4b7a6d536be47a783d0ae56ba"></audio>
    </div>
    <script>
        const $ = document;
        const loaderp = $.querySelector('.loader')
        const container = $.querySelector('.container')
        const pagem = $.querySelector('.page')
        const dozP = $.getElementById('dozpage')
        const optionn = $.querySelector('.option')
        const line = $.querySelectorAll('.line');
        const circles = $.querySelectorAll('.circles');
        const optm = $.querySelectorAll('.page div')
        const omenu = $.querySelector('.mymenu')
        const imgbac = $.querySelectorAll('.option picture img')
        const colors = $.querySelectorAll('.colorm .color')
        const tayiid = $.getElementById('tayid')
        const message = $.querySelector('.message')
        const messagem = $.querySelectorAll('.message div')
        const audioo = $.querySelectorAll('audio')
        const colorb = [
            'rgb(0, 0, 0)',
            'rgb(0, 0, 106)',
            'rgb(14, 42, 3)'
        ]
        const colorer = [
            'rgb(255, 0, 0)',
            'rgb(0, 238, 255)',
            'rgb(211, 255, 54)'
        ]
        let player = 1
        let backgc = 1
        let colornb = 1
        let colornr = 1
        let mohre = 24
        let siah = 12
        let germez = 12
        let siahz = 0
        let germezz = 0
        let blackm = []
        let cln = ''
        let cnn = ''
        let clwn = ''
        let clr  = ''
        let clll = ''
        let clwl = ''
        let clb  = ''
        let cll = ''
        let clw = ''
        let firsm = ''
        let secm = ''
        let thirsm = ''
        let clww = ''
        let firsw = ''
        let secw = ''
        let firsch = ''
        let secondch = ''
        let thirsch = ''
        let deln = ''
        let colredm = 0 

        window.addEventListener('load', () => loaderp.style.display = 'none')

        setInterval( () => {
            if(navigator.onLine){
                if(backgc == 1){
                    container.style.background = 'url(\'https://s31.picofile.com/file/8468775242/WallpaperGram_IR_1562149262_z18163.jpg\')'
                }else if (backgc == 2){
                    container.style.background = 'url(\'https://s30.picofile.com/file/8468987350/WallpaperGram_IR_1561887212_z49360.jpg\')'
                }else if (backgc = 3){
                    container.style.background = 'url(\'https://s31.picofile.com/file/8467765418/background3.png\')'
                }
            }else {
                container.style.backgroundColor = 'rgb(55, 122, 55)'
            }
            let widthpa = window.screen.availWidth
            let heightpa = window.screen.availHeight
            if (heightpa > widthpa) {
                dozP.style.width = (widthpa - (widthpa * .15)) + 'px'
                dozP.style.height = (widthpa - (widthpa * .15)) + 'px'
                pagem.style.width = (widthpa - (widthpa * .15)) + 'px'
                pagem.style.height = (widthpa - (widthpa * .15)) + 'px'
                optionn.style.width = (widthpa - (widthpa * .15)) + 'px'
                optionn.style.height = (widthpa - (widthpa * .15)) + 'px'
            }else if (widthpa > heightpa) {
                dozP.style.width =  (heightpa - (heightpa * .15)) + 'px'
                dozP.style.height =  (heightpa - (heightpa * .15)) + 'px'
                pagem.style.width =  (heightpa - (heightpa * .15)) + 'px'
                pagem.style.height =  (heightpa - (heightpa * .15)) + 'px'
                optionn.style.width =  (heightpa - (heightpa * .15)) + 'px'
                optionn.style.height =  (heightpa - (heightpa * .15)) + 'px'   
            }
            if(audioo.currentTime > 160){
                audioo.currentTime = '0'
            }
        },500)

        colornb = 0
        colornr = 0

        messagem[0].addEventListener('click', () => {
            message.style.display = 'none'
            optionn.style.display = 'grid'
        })
        messagem[1].addEventListener('click', () => message.style.display = 'none' )

        imgbac[0].addEventListener('click', () => backgc = 1 )
        imgbac[1].addEventListener('click', () => backgc = 2 )
        imgbac[2].addEventListener('click', () => backgc = 3 )

        colors[0].addEventListener('click', e => {
            colornb = 0
            if( colors[1].classList.contains('active')){
                colors[1].classList.remove('active')
            }else if(colors[2].classList.contains('active')){
                colors[2].classList.remove('active')
            }
            e.target.classList.add('active')
        })
        colors[1].addEventListener('click', e => {
            colornb = 1
            if(colors[0].classList.contains('active')){
                colors[0].classList.remove('active')
            }else if(colors[2].classList.contains('active')){
                colors[2].classList.remove('active')
            }
            e.target.classList.add('active')
        })
        colors[2].addEventListener('click', e => {
            colornb = 2
            if( colors[1].classList.contains('active')){
                colors[1].classList.remove('active')
            }else if(colors[0].classList.contains('active')){
                colors[0].classList.remove('active')
            }
            e.target.classList.add('active')
        })
        colors[3].addEventListener('click', e => {
            colornr = 0
            if( colors[4].classList.contains('active')){
                colors[4].classList.remove('active')
            }else if(colors[5].classList.contains('active')){
                colors[5].classList.remove('active')
            }
            e.target.classList.add('active')
        })
        colors[4].addEventListener('click', e => {
            colornr = 1
            if( colors[3].classList.contains('active')){
                colors[3].classList.remove('active')
            }else if(colors[5].classList.contains('active')){
                colors[5].classList.remove('active')
            }
            e.target.classList.add('active')
        })
        colors[5].addEventListener('click', e => {
            colornr = 2
            if( colors[4].classList.contains('active')){
                colors[4].classList.remove('active')
            }else if(colors[3].classList.contains('active')){
                colors[3].classList.remove('active')
            }
            e.target.classList.add('active')
        })

        tayiid.addEventListener('click', () => {
            circles.forEach( e => e.style.backgroundColor = '')
            optionn.style.display = 'none'
        })

        omenu.addEventListener('click', () => {
            pagem.style.display = 'grid'
            dozP.style.display = 'none'
            audioo[0].pause()
    })

        optm[0].addEventListener('click', () => {
            if(!(message.style.display == 'block')){
                pagem.style.display = 'none'
                dozP.style.display = 'grid'
                audioo[0].play()
            }
        })
        optm[1].addEventListener('click', () => {
            if(!(message.style.display == 'block')){
                circles.forEach( e => e.style.backgroundColor = '')
                mohre = 24
                siah = 12
                germez = 12
                pagem.style.display = 'none'
                dozP.style.display = 'grid'
                audioo[0].play()
            }
        })
        optm[2].addEventListener('click', () => {
            if(!(message.style.display == 'block')){
                circles.forEach( e => {
                    if(e.style.backgroundColor !== '') {
                        colredm += 1
                    }
                })
                if(colredm > 0) {
                    message.style.display = 'block'
                    colredm = 0
                }else {
                    optionn.style.display = 'grid'
                }
            }
        })
        optm[3].addEventListener('click', () => {
            if(!(message.style.display == 'block')){
                alert('این بازی توسط ابوالفضل الماسیان طراحی شده \n اگر مشکلی داشت می توانید با شماره 09374337225 تماس بگیرید')   
            }
        })

        circles.forEach( e => e.addEventListener('click', event => {
            cln = event.target.className
            cnn = cln[cln.length - 1]
            clww = cln[cln.length - 2]
            clwn = clww + cnn
            if(mohre > 0){
                if( player == 1 && event.target.style.backgroundColor == '') {
                    mohre--
                    player++
                    siahz++
                    clb = event.target.className
                    cll = clb[clb.length - 1]
                    clw = clb[clb.length - 2] + cll
                    check3(colorb[colornb], clw)
                    console.log(audioo[1]);
                }else if(player == 2 && event.target.style.backgroundColor == '') {
                    mohre--
                    player--
                    germezz++
                    clb = event.target.className
                    cll = clb[clb.length - 1]
                    clw = clb[clb.length - 2] + cll
                    check3(colorer[colornr], clw)
                }
            }else if (player == 1 && event.target.style.backgroundColor === colorb[colornb]) {
                check()
            }else if (player == 2 && event.target.style.backgroundColor === colorer[colornb]) {
                check()
            }else if (event.target.style.backgroundColor == '') {
                circles.forEach( e => {
                    if( event.target.classList.contains('dop') && e.classList.contains(deln)) {
                        e.style.backgroundColor = ''
                    }
                })
                if( player == 1 && e.classList.contains('dop')) {
                    event.target.style.backgroundColor = colorb[colornb]
                    player++
                    circles.forEach( e => {
                        if(e.classList.contains('dop')) {
                            e.classList.remove('dop')
                        }
                    })
                    cln = event.target.className
                    cnn = cln[cln.length - 1]
                    clww = cln[cln.length - 2]
                    clwn = clww + cnn
                    check3(colorb[colornb], clwn)
                }else if ( player == 2 && e.classList.contains('dop')) {
                    event.target.style.backgroundColor = colorer[colornr] 
                    player--
                    circles.forEach( e => {
                        if(e.classList.contains('dop')) {
                            e.classList.remove('dop')
                        }
                    })
                    cln = event.target.className
                    cnn = cln[cln.length - 1]
                    clww = cln[cln.length - 2]
                    clwn = clww + cnn
                    check3(colorer[colornr], clwn)
                }
            }
            function check3 (col, numb) {
                event.target.style.backgroundColor = col
                if((( numb == 'a1' || numb == 'a2' || numb == 'a3' ) && (circles[0].style.backgroundColor === col && circles[1].style.backgroundColor === col && circles[2].style.backgroundColor === col )) || (( numb == 'a1' || numb == 'a4' || numb == 'a7') && (circles[0].style.backgroundColor === col && circles[3].style.backgroundColor === col && circles[6].style.backgroundColor === col )) || ((numb == 'a1' || numb == 'b1' || numb == 'd1') && (circles[0].style.backgroundColor === col && circles[9].style.backgroundColor === col && circles[18].style.backgroundColor === col))){ checkb(player)
                }else if((( numb == 'a9' || numb == 'a8' || numb == 'a7' ) && (circles[8].style.backgroundColor === col && circles[7].style.backgroundColor === col && circles[6].style.backgroundColor === col )) || (( numb == 'a9' || numb == 'a6' |numb == 'a3') && (circles[8].style.backgroundColor === col && circles[5].style.backgroundColor === col && circles[2].style.backgroundColor === col )) || ((numb == 'a9' || numb == 'b9' || numb == 'd9') && (circles[8].style.backgroundColor === col && circles[17].style.backgroundColor === col && circles[26].style.backgroundColor === col ))){ checkb(player)
                }else if ((( numb == 'a2' || numb == 'b2' || numb == 'd2' ) && (circles[1].style.backgroundColor === col && circles[10].style.backgroundColor === col && circles[19].style.backgroundColor === col ))){ checkb(player)
                }else if (( numb == 'a4' || numb == 'b4' || numb == 'd4' ) && (circles[3].style.backgroundColor === col && circles[12].style.backgroundColor === col && circles[21].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'a6' || numb == 'b6' || numb == 'd6' ) && (circles[5].style.backgroundColor === col && circles[14].style.backgroundColor === col && circles[23].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'a8' || numb == 'b8' || numb == 'd8' ) && (circles[7].style.backgroundColor === col && circles[16].style.backgroundColor === col && circles[25].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'b1' || numb == 'b2' || numb == 'b3' ) && (circles[9].style.backgroundColor === col && circles[10].style.backgroundColor === col && circles[11].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'b1' || numb == 'b4' || numb == 'b7' ) && (circles[9].style.backgroundColor === col && circles[12].style.backgroundColor === col && circles[15].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'b9' || numb == 'b6' || numb == 'b3' ) && (circles[11].style.backgroundColor === col && circles[14].style.backgroundColor === col && circles[17].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'b9' || numb == 'b8' || numb == 'b7' ) && (circles[17].style.backgroundColor === col && circles[16].style.backgroundColor === col && circles[15].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'd1' || numb == 'd2' || numb == 'd3' ) && (circles[18].style.backgroundColor === col && circles[19].style.backgroundColor === col && circles[20].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'd1' || numb == 'd4' || numb == 'd7' ) && (circles[18].style.backgroundColor === col && circles[21].style.backgroundColor === col && circles[24].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'd9' || numb == 'd6' || numb == 'd3' ) && (circles[20].style.backgroundColor === col && circles[23].style.backgroundColor === col && circles[26].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'a7' || numb == 'b7' || numb == 'd7' ) && (circles[6].style.backgroundColor === col && circles[15].style.backgroundColor === col && circles[24].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'a3' || numb == 'b3' || numb == 'd3' ) && (circles[2].style.backgroundColor === col && circles[11].style.backgroundColor === col && circles[20].style.backgroundColor === col )){ checkb(player)
                }else if (( numb == 'd9' || numb == 'd8' || numb == 'd7' ) && (circles[24].style.backgroundColor === col && circles[25].style.backgroundColor === col && circles[26].style.backgroundColor === col )){ checkb(player)}
            }
            function check () {
                deln = clwn
                if(event.target.classList.contains('dop')){
                    if(event.target.style.backgroundColor == colorb[colornb]) {
                        siah--
                        if(siah < 3){
                            alert('مهره ی قرمز برنده بازی شد')
                            circles.forEach( e => {
                                e.style.backgroundColor = ''
                            })
                            mohre = 24
                            siah = 12
                            germez = 12
                            pagem.style.display = 'grid'
                        }
                    }else if(event.target.style.backgroundColor == colorer[colornb]) { 
                        germez--
                        if(germez < 3){
                            alert('مهره ی سیاه برنده بازی شد')
                            circles.forEach( e => {
                                e.style.backgroundColor = ''
                            })
                            mohre = 24
                            siah = 12
                            germez = 12
                            pagem.style.display = 'grid'
                        }
                    }
                    event.target.style.backgroundColor = ''
                    circles.forEach( e => {
                        if(e.classList.contains('dop')) {
                            e.classList.remove('dop')
                        }
                    })
                }else if (siah == 3 || germez == 3){
                        circles.forEach( e => {
                            if( e.style.backgroundColor == ''){
                                e.classList.add('dop')
                            }
                        })
                }else{
                    circles.forEach( e => {
                        if(e.classList.contains('dop')) {
                            e.classList.remove('dop')
                        }
                    })
                    if(cnn == 1) {
                        firsm = 4
                        secm = 1
                        thirsm = 2   
                    }else if (cnn == 2) {
                        firsm = 1
                        secm = 2
                        thirsm  = 3
                    }else if (cnn == 3){
                        firsm = 2
                        secm = 3
                        thirsm = 6
                    }else if (cnn == 4){
                        firsm = 1
                        secm = 4
                        thirsm = 7
                    }
                    else if (cnn == 6){
                        firsm = 3
                        secm = 6
                        thirsm = 9
                    }else if (cnn == 7){
                        firsm = 4
                        secm = 7
                        thirsm = 8
                    }else if (cnn == 8){
                        firsm = 7
                        secm = 8
                        thirsm = 9
                    }else if (cnn == 9){
                        firsm = 8
                        secm = 9
                        thirsm = 6
                    }
                    if (clww == 'a'){
                        firsch = circles.forEach ( e => {
                            if( e.classList.contains(clww + firsm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                        secondch = circles.forEach ( e => {
                            if( e.classList.contains('b'+ secm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                        thirsch = circles.forEach ( e => {
                            if( e.classList.contains('a'+ thirsm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                    }else if(clww == 'b') {
                        firsch = circles.forEach ( e => {
                            if( e.classList.contains(clww + firsm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                        secondch = circles.forEach ( e => {
                            if( e.classList.contains('a'+ secm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                            if( e.classList.contains('d'+ secm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                        thirsch = circles.forEach ( e => {
                            if( e.classList.contains(clww + thirsm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                    }
                    else if(clww == 'd') {
                        firsch = circles.forEach ( e => {
                            if( e.classList.contains(clww + firsm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                        secondch = circles.forEach ( e => {
                            if( e.classList.contains('b'+ secm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                        thirsch = circles.forEach ( e => {
                            if( e.classList.contains(clww + thirsm)){
                                if(e.style.backgroundColor == ''){e.classList.add('dop')}
                            }
                        })
                    }
                }
            }
            function checkb (num) {
                if(num == 2){
                    if (mohre > 0){
                        siah--
                        mohre--
                    }else {
                        circles.forEach( e => {
                            if( e.style.backgroundColor == colorer[colornr] ){
                                e.classList.add('dop')
                            }
                        })
                    }
                }else {
                    if (mohre > 0){
                        germez--
                        mohre--
                    }else {
                        circles.forEach( e => {
                            if( e.style.backgroundColor == colorb[colornr] ){
                                e.classList.add('dop')
                            }
                        })
                    }
                }
            }
        }))
        // function end () {

        // }
        </script>
</body>
</html>
