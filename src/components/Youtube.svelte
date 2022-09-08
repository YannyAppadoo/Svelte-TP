<script context="module">
    // 2. This code loads the IFrame Player API code asynchronously.
    var tag = document.createElement('script');

    tag.src = "https://www.youtube.com/iframe_api";
    var firstScriptTag = document.getElementsByTagName('script')[0];
    firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

    window.onYouTubeIframeAPIReady = function() {
        //console.log('hello')
        window.dispatchEvent(new Event("YoutubeIframeAPIReady"))
    }
</script>

<script>
    let player;
    let divId = "player_"+parseInt(Math.random() * 100000).toString()
    export let videoId;
    window.addEventListener("YoutubeIframeAPIReady", function(){
        console.log('load player...')  
        player = new YT.Player(divId, {
         height: '360',
         width: '640',
         videoId: videoId,
         events: {
           //'onReady': onPlayerReady,
           //'onStateChange': onPlayerStateChange
         }
       });
    })

    export function playVideo(){
        player.playVideo()
    }
 

</script>

<h2></h2> <br>
<div id={divId}></div>


<style>
    h1{
        color:yellow;
        margin: 2rem auto;
        display: flex;
        justify-content: center;
        font-family: 'Exo';
        text-shadow: 
        0 1px 0 rgb(235, 46, 46), 
        0 2px 0 #c21a1a,
        0 3px 0 #e52a2a,
        0 4px 0 #ff4b4b,
        0 5px 0 #c92626,
        0 6px 1px rgba(var(--couleur),.1),
        0 0 5px rgba(var(--couleur),.1),
        0 1px 3px rgba(var(--couleur),.3),
        0 3px 5px rgba(var(--couleur),.3),
        0 5px 10px rgba(var(--couleur),.25),
        0 10px 10px rgba(var(--couleur),.2),
        0 20px 20px rgba(var(--couleur),.15);
	
    }
</style>