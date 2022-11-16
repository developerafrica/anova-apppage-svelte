<script>
	import Router from "svelte-spa-router";
	import {link} from "svelte-spa-router";
	import Home from "./routes/index.svelte";
	import Footer from "./components/footer.svelte"
	export let version;
	

	$:clip = false;
	$:toggleOne = false;
	$:toggleTwo = true;
	$:toggleThree = true;
</script>
<Router routes={{
	"/": Home
}}/>
<section id="layout">
	<nav class="navigation">
		<div class="nv">

			<div class="brand">
				<h1>DEVELOPER AFRICA MW</h1>						
				
			</div>

			<div class="options">
				<div class="opt">
					
					<div on:click={()=>{clip = !clip}} class="menu">
						<div class="mn">
							<svg width="35" height="35" viewBox="0 0 35 35" fill="none" xmlns="http://www.w3.org/2000/svg">
								<rect width="35" height="35" rx="10" fill="#006612"/>

								</svg>
								
						</div>
					</div>
				</div>   
			</div>

		</div>
	</nav>

	<div class:clip={clip} class="toogle">
		<div class="tg">
			<div class="content">
				<div class="cnt">		
					<div class="top">
						<div class="tp">
							<div class="tp-img">
								<img src="./favicon.png" alt="logo" width="65px" />								
							</div>
							<div class="tp-text">
								<h1>LUANAR ANOVA STATISTICS</h1>
								<p>VERSION : {version}</p>
							</div>
						</div>
					</div>
					<div class="text">
						<p># DESIGN AND ANALYSIS OF EXPERIMENTS  </p>
					</div>
					<div class="middle">
						<div class="md">
							<ul >
								<li><a href="https://luanaranovaonline.netlify.app">ANOVA ONLINE</a></li>
								<li><a href="tel://0880164455">CONTACT</a></li>

							</ul>
						</div>
					</div>
					<div class="bottom"></div>
				
				</div>
			</div>
			<div class="copy">
				<a href="http://butaopeter.netlify.app">
					 <p>2022 BUTAO PETER | DEVELOPERAFRICAMW</p>
				</a>
			</div>
		

		</div>
	</div>

	<Footer />
	
</section>

<style lang="scss">
	:global(body){
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	:root{
		--bc: #278deb;
		--lbc: #278ceb23;
		--dbc:#154d80;
		--gc: #006612;
		--lgc: #00661335;
		--dtc: black;
		--wtc:  seashell;
		--jr: #E99E3C;
	}
	@mixin font($c, $s, $w) {
        font-family:Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing:antialiased;
        -moz-osx-font-smoothing:grayscale;
        color:$c;
        font-size: $s;
        font-weight:$w;

    }
	#layout{
		.navigation{
			position: fixed; 
			top:0;
			left: 0;
			width: 100%;
			z-index:9;

			.nv{
				display: flex;
				justify-content: space-between;
				align-items: center;
				padding: 0.5rem;
				margin: auto;
				background: white;

				//brand / logo name section
				.brand{
					h1{
						@include font(var(--dtc), 0.8rem, 500);
						padding: 0px 10px;
						margin: 0;
					}
					
				}

				//jere section
				.options{					
					.opt{
						// toogle menu section
						.menu{
							.mn{
								padding: 0.5rem;
							}

						}
					}
				}
			}
		}
		
		.toogle{
		//	background: #d7eafb;
			background: var(--gc);
			position: fixed;
			width:  100%;
			height: 100vh;
			top: 0;
			right: 0;
			z-index: 8;
			pointer-events: none;
			clip-path: circle(0px at 90%);
			-webkit-clip-path: circle(0px at 90%);
			transition: 1s all ease-in-out;
			.tg{

				width: 100%;
				height: 100%;
				display:flex;
				flex-direction: column;
				.copy{
					text-align: center;
					position: relative;
					left:0;
					background: white;
					margin-top: auto !important;					
					box-shadow: rgba(0, 0, 0, 0.39) 0 -0.3125rem 6px 1px;
					p{
						@include font(var(--dtc), 12px, 500)
					}
				}
				.content{
					padding-right: 1.25rem;
					padding-left: 0.625rem;
					padding-right: 0.625rem;
					
					.cnt{
						padding-top: 10vh;
						
						.top{
							.tp{
								display: flex;
								align-items: center;
								padding-bottom: 0.625rem;
								border-bottom: var(--bc) solid 1px;
								.tp-text{
									padding: 0 0.9375rem;
									h1{
										@include font(var(--wtc), 0.875rem, 500);
										margin: 0.3125rem 0;
										padding:0;
									}
									p{
										@include font(var(--wtc), 0.55rem, 550);
										margin: 0;
										padding:0;
									}
								}
							}
						}
						.text{
							text-align: center;
							p{
								@include font(gray, 0.875rem, 550);
								letter-spacing: 0.125rem;
								padding: 10px 0;
							}
						}
						.middle{
							.md{
								ul{
									list-style: none;
									padding: 0;
									li{
										margin: 15px 0;
										a{
											display: block;
											padding: 15px 0;
											@include font(var(--wtc), 15px, 550);
										}
									}
									
								}
							}
						}
					}
				}

			}
		}
		//js class
		.clip{
			pointer-events: all;
			clip-path: circle(1200px at 90%);
			-webkit-clip-path: circle(1200px at 90%);
		}
	}
	@media only screen and (min-width: 1000px){
		:global(body){
			margin: auto;
			max-width: 700px;

		}
		#layout{
			.navigation{
				.nv{
					background: none;
				}
			}
			.toogle{
			pointer-events: all;
			width: 20%;
			margin: 20px;
			border-radius: 5px;
			clip-path: none;
			-webkit-clip-path: none;
			.text{
				p{
					font-size: 11px !important;
				}
			}
		
			.copy{
				display: none;
			}

			}
			.options{
				opacity: 0;
			}
		}
	}
	


</style>