<script>
    $: pop = false
</script>
<div class="home">
    <div class="hm">
        <div class="upper-txt">
            <div class="uptxt">
                <h1>ANOVA STATISTICS</h1>
                <p>SIMPLIFY YOUR STUDENT PRODUCTIVITY</p>
            </div>
        </div>
        <div class="image">
            <img src="/assets/design.png" alt="software design">
         
        </div>
        <div on:click={()=>{pop = !pop}} class:popped={pop} class="pop">
            <div class="pp">
                <h1>DESKTOP APPLICATION NOT AVAILABLE</h1>
                <h2>under construction</h2>
                <p>please use the online version while waiting</p>
                <a href="https://luanaranovaonline.netlify.app">ANOVA ONLINE</a>
            </div>
        </div>
        <div class="download"><button on:click={()=>{pop = !pop}} >DOWNLOAD</button><div class="line">___</div></div>
    </div>
</div>
<style lang="scss">
       @mixin font($c, $s, $w){
        font-size: $s;
        font-weight: $w;
        color: $c;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
    .popped{
        clip-path: circle(1500px) !important;
        pointer-events: all !important;
        transition: all 1s ease;

    }
    .pop{
        text-align: center;
        top:0;
        left: 0;
        height: 100vh;
        background: rgba(0, 0, 0, 0.435);
        position: fixed;
        width: 100%;
        clip-path: circle(0);
        pointer-events: none;
        z-index: 20;
        display: flex;
        align-items: center;
        justify-content: center;
        .pp{
            margin: 15px;
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: rgba(0, 0, 0, 0.404) 0 4px 4px 0;
            h1{
                @include font(var(--dtc), 14px, 550)
            }
            h2{
                @include font(var(--dtc), 13px, 550)
            }
            p{
                @include font(var(--dtc), 12px, 550);
                padding: 10px 0;
            }
            a{
                @include font(var(--dtc), 13px, 550);
                border: var(--gc) solid 1px;
                padding: 10px;
                border-radius: 5px;
                margin: 15px 0;
            }
        }
    }
    .home{
        text-align: center;
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        .image{
            padding: 50px 0 0 0 ;
            img{
                width: 100%;

            }
        }
        .download{
            text-align: center;
            position: fixed;
            left: 0;
            bottom: 0;
            width: 100%;
            .line{
                background-color: black;
                width: 90px;
                height: 3px;
                margin: 10px auto;
            
            }
            button{
                border: black solid 1px;
                border-radius: 7px;
                background:white;
                padding: 10px 20px;
            }
        }


    }
    @media only screen and (min-width: 700px){
        .home{
            .image{
                width: 500px;
                img{
                    width: 100%;
                }
            }
        }
        
    }
</style>