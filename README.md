# Google Meet - Watch Party

Host your very own Watch Party with Popular Web-based streaming platforms using Google Meet - Watch Party!
Let the audience control the playing of the movie (Play and Pause).


### Steps to use:
- Create a bookmarklet with the following script
- Click the Copy Button on the right of this code.

      javascript:!function(){var mic=document.querySelector("[data-is-muted]"),parent=mic.parentElement.parentElement.parentElement.parentElement.parentElement,rightnotif=parent.children[10],targetNode=rightnotif,bottom=parent.children[8],config={attributes:!0,childList:!0,subtree:!0};css=document.createElement("style"),css.innerHTML=".e-card{background:#222;color:#eee;user-select: none;padding:10px;width:100%;filter:invert(.8);border-radius:50px;margin:10px}.e-button{appearance:none;border:none;border-radius:50%;height:40px;width:40px;cursor:pointer;transition:.4s ease;float:right;margin:-4px}.e-button:hover{background:#7fffd4;}.e-title{margin:10px;font-weight: 600;}",document.head.appendChild(css);var movieTab=!1,callbackMonitor=function(e){msg=rightnotif.children[0].children[2].children[0].children[0].children[2].innerText,movieTab?movieTab.postMessage(msg,"*"):console.log("Tab not Open, ReHost Party"),chatListObserver&&(chatListObserver.disconnect(),chatListObserver=!1),console.log(msg)};bottom.children[2].children[3].addEventListener("click",()=>{setTimeout(()=>{bottomMenu=document.querySelectorAll('[role="menu"]')[0],ChgLayout=bottomMenu.children[0].children[0].children[0],MovieParty=ChgLayout.cloneNode(1),MovieParty.removeAttribute("jsslot"),MovieParty.children[2].children[0].children[0].innerText="Watch Party",MovieParty.children[1].children[0].innerHTML='<span class="google-material-icons">theaters</span>',MovieParty.children[2].children[0].children[1].innerText="Host a Watch Party",MovieParty.addEventListener("click",OpenMovieTab),document.getElementById("movieParty")||(MovieParty.id="movieParty",bottomMenu.children[0].children[0].insertBefore(MovieParty,ChgLayout))},200)});var chatListObserver=!1;function RenderChatCommands(){for(chatListObserver&&(chatListObserver.disconnect(),chatListObserver=!1),chatsList=parent.children[3].children[0].children[1].children[1].children[1].children[1].children[0].children[1].children,i=0;i<chatsList.length;i++)for(chatMsgs=chatsList[i].children,j=0;j<chatMsgs.length;j++)chatMsgs[j].innerText.includes(">cmd")&&(chatsList[i].children[1].style.width="85%",ele=RenderControl(chatMsgs[j].innerText),chatMsgs[j].innerHTML="",chatMsgs[j].appendChild(ele));chatListObserver||(chatsList=parent.children[3].children[0].children[1].children[1].children[1].children[1].children[0].children[1],(chatListObserver=new MutationObserver(rescan)).observe(chatsList,config))}function RenderControl(e){return action=e.split(" ")[1],html='<div class="e-card"><button class="e-button google-material-icons">play_arrow</button><p class="e-title">Player Control</p></div>',div=document.createElement("div"),div.innerHTML=html,"play"==action?(div.children[0].children[0].innerText="pause",div.children[0].children[1].innerText="Player is Resumed",div.children[0].children[0].addEventListener("click",()=>{command(">cmd pause")})):"pause"==action?(div.children[0].children[0].innerText="play_arrow",div.children[0].children[1].innerText="Player is Paused",div.children[0].children[0].addEventListener("click",()=>{command(">cmd play")})):(div.children[0].children[0].innerText="play_arrow",div.children[0].children[1].innerText="Player Control",div.children[0].children[0].addEventListener("click",()=>{command(">cmd play")})),div.children[0]}function command(e){chatBox=document.getElementsByTagName("textarea")[0],chatBox.parentElement.parentElement.children[0].innerText="",chatBox.style.height="50px",chatBox.value=e+" *"}chatButton=parent.children[0].children[2].children[0].children[1].children[2],chatButton.addEventListener("click",()=>{setTimeout(()=>{RenderChatCommands()},300),rescan=function(e){RenderChatCommands()},chatsList=parent.children[3].children[0].children[1].children[1].children[1].children[1].children[0].children[1],(chatListObserver=new MutationObserver(rescan)).observe(chatsList,config)});var OpenMovieTab=function(){movieTab=window.open("https://elvistony.github.io/watchparty/#load-media","Media Source")},observer=new MutationObserver(callbackMonitor);observer.observe(targetNode,config);}();

- Create a new Bookmark with a title of your choice, paste the code as the URL.
- Open the Google meet where the stream will begin and click the bookmarklet while you are in the page.
- Now if you are just a watcher, you can stop here and go to [Controls](#controls).
#### For the Host
- Follow the above steps and then,
- Create a new Watch Party from the options in Google Meet
- Create another Bookmarklet "Watch Party Player" with the below code.
 
      javascript:!function(){function e(e,t=5e3){toast.children[1].innerText=e,toast.classList.remove("hide"),setTimeout(()=>{toast.classList.add("hide")},5e3)}state=!1,toast=document.createElement("div"),toast.innerHTML='<span onclick="toast.classList.add(\'hide\')" class="toast-close"> &#x2715 </span><p class="toast-msg">📺 Movie Party</p>',toast.classList.add("toast"),document.body.appendChild(toast),css=document.createElement("style"),css.innerHTML=".toast-msg{padding:10px;}.toast{z-index:100000;user-select:none;font-size:1.3em;position:absolute;background:#141b29;color:#576580;font-family:sans-serif;padding:5px 20px;border-radius:50px;width:155px;top:5%;right:2%;transition:1s ease;}.toast-close{position:relative;float:right;height:20px;width:20px;color:#141b29;background:#576580;padding:10px;right:-14px;border-radius:50%;transition:.3s ease;text-align:center;cursor:pointer}.toast-close:hover{color:#576580;background:#141b29}.hide{opacity:0}",document.head.appendChild(css),setTimeout(()=>{document.getElementsByTagName("video")[0].pause()},1e3),window.addEventListener("message",t=>{msg=t.data,cmd=msg.split(" "),"play"==cmd[1]?(document.getElementsByTagName("video")[0].play(),e("Resuming Player",3e3)):"pause"==cmd[1]?(document.getElementsByTagName("video")[0].pause(),e("Pausing Player")):console.log("Unknown Command",msg)})}();
      
- This opens a new tab, Paste the URL of the platform page and click Load Media.
- Click the bookmarklet while you are in the Movie Page.
- Share the `Tab` where the video was loaded (Best Video Resolutions work with Sharing Tabs)
- Close the message side-bar. (This is important!)
- Voila! Its Ready.
    
 # Controls
 - To Pause the player (only audience) type `>cmd pause` in the chat box and send.
 - To Resume the player (if you're audience) type `>cmd play` in the chat box and send.

### Note
- Audience can skip installing both and manually type the commands.
- The Script renders the command messages to quick toggles for simpler use.

### Issues
- **Reason for using the Tab Opened by Meet**
      - Browsers do not allow communication between tabs common tabs. Tabs opened by Google Meet can communicate with each other.
- Toggles can only paste the text, the user must send it manually due to Google Meet's security policies.
- will probably have lot more...
