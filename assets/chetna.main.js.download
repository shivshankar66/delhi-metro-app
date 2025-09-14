const LOGO_URL = "https://chatbot.delhimetrorail.com/render/logo-anim.gif";
const CLOSE_ICON = `<svg fill="#ffffff" height="2.0vh" width="2.0vh" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="-98 -98 686.00 686.00" xml:space="preserve" stroke="#ffffff" stroke-width="24.5"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <polygon points="456.851,0 245,212.564 33.149,0 0.708,32.337 212.669,245.004 0.708,457.678 33.149,490 245,277.443 456.851,490 489.292,457.678 277.331,245.004 489.292,32.337 "></polygon> </g></svg>`;
const CLOSE_ICON_DARK = `<svg fill="#000000" height="2.0vh" width="2.0vh" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="-98 -98 686.00 686.00" xml:space="preserve" stroke="#000000" stroke-width="24.5"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <polygon points="456.851,0 245,212.564 33.149,0 0.708,32.337 212.669,245.004 0.708,457.678 33.149,490 245,277.443 456.851,490 489.292,457.678 277.331,245.004 489.292,32.337 "></polygon> </g></svg>`;
const LAUNCHER_CSS = `background-size: cover;
background-position: 0.6vh -0.3vh;
background-repeat: no-repeat;
background-color: white;
width: 10vh;
height: 10vh;
-webkit-box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
-webkit-backface-visibility: hidden;
-webkit-transition: all 0.5s; 
transition: all 0.5s; 
cursor: pointer; 
z-index: 9; 
border-top-left-radius: 100%;
border-top-right-radius: 100%;
border-bottom-left-radius: 100%;
display: flex;
justify-content: center;
align-items: center;`;

const INIT_CSS = `position: fixed;
z-index: 999999999;
background-color: transparent;
display: flex;
justify-content: flex-end;
// align-items: center;
bottom: 5.4vh;
right: 2vh;
width: fit-content;
max-width: 95%;
flex-direction: column;
align-items: end;
bottom: 6vh;
gap: 7px;
`;

const FULL_DISPLAY_CSS = `border-radius: 8px;
box-sizing: border-box;
right: 0; 
width: 55vh !important; 
max-width: none; 
position: fixed; 
z-index: 1000; 
bottom: 0px; 
visibility: visible; 
opacity: 1;
box-shadow: 0 7px 6px 1px rgb(0 0 0 / 16%); 
-webkit-box-shadow: 0 7px 6px 1px rgb(0 0 0 / 16%); 
-moz-box-shadow: 0 7px 6px 1px rgba(0,0,0,.16); 
height: 80%;
right: 3.2vh;`;

const MOBILE_CSS = `border-radius: 8px; 
box-sizing: border-box;
right: 0; 
width: 100% !important;
max-width: none; 
position: fixed; 
z-index: 1000;
bottom: 0px; 
visibility: visible; 
opacity: 1;
box-shadow: 0 7px 6px 1px rgb(0 0 0 / 16%);
-webkit-box-shadow: 0 7px 6px 1px rgb(0 0 0 / 16%); 
-moz-box-shadow: 0 7px 6px 1px rgba(0,0,0,.16); 
height: 100%;`;

const BOTTOM_LABEL_CSS = `padding: .8vh;
background: white;
position: fixed;
bottom: 1.0vh;
border-top-left-radius: 8px;
border-bottom-left-radius: 8px;
border-bottom-right-radius: 8px;
-webkit-box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
-webkit-backface-visibility: hidden; 
-webkit-transition: all 0.5s;
cursor: pointer;
font-size: 1.6vh;
height: fit-content;`;

const HOVER_CSS = `padding: .8vh;
bottom: 16.5vh;
background: white;
// position: fixed;
border-radius: .8vh;
-webkit-box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
-webkit-backface-visibility: hidden; 
-webkit-transition: all 0.5s;
display: none;
font-size: 1.6vh;
height: fit-content;`;

const ANIMATION_CSS = `<style>.shaker {
  animation: shake 0.2s;

  animation-iteration-count: infinite;
}

@keyframes shake {
  0% { transform: translate(1px, 1px) rotate(0deg); }
  10% { transform: translate(-1px, -2px) rotate(-1deg); }
  20% { transform: translate(-3px, 0px) rotate(1deg); }
  30% { transform: translate(3px, 2px) rotate(0deg); }
  40% { transform: translate(1px, -1px) rotate(1deg); }
  50% { transform: translate(-1px, 2px) rotate(-1deg); }
  60% { transform: translate(-3px, 1px) rotate(0deg); }
  70% { transform: translate(3px, 1px) rotate(-1deg); }
  80% { transform: translate(-1px, -1px) rotate(1deg); }
  90% { transform: translate(1px, 2px) rotate(0deg); }
  100% { transform: translate(1px, -2px) rotate(-1deg); }
}</style>`;

let isOpen = false;
let lang = "en";

const iframe = document.createElement("iframe");
const launcher = document.createElement("div");
const mainDiv = document.createElement("div");
const close = document.createElement("div");
const bottomInfo = document.createElement("div");
const hoverInfo = document.createElement("div");

const fixCSS = () => {
  if (isOpen) {
    launcher.style.display = "none";
    iframe.style.display = "block";
    mainDiv.style.cssText =
      window.innerWidth <= 416 ? MOBILE_CSS : FULL_DISPLAY_CSS;
    close.style.display = "block";
  } else {
    iframe.style.display = "none";
    launcher.style.display = "flex";
    mainDiv.style.cssText = INIT_CSS;
    close.style.display = "none";
  }
};

const setIframe = () => {
  iframe.className = "dmrc_frame";
  iframe.id = "dmrc_chatbot";
  iframe.setAttribute(
    "allow",
    "geolocation https://chatbot.delhimetrorail.com/; microphone https://chatbot.delhimetrorail.com/; camera; otp-credentials; midi; accelerometer; gyroscope; payment"
  );
  iframe.style.width = "100%";
  iframe.style.height = "100%";
  iframe.style.position = "relative";
  iframe.style.margin = 0;
  iframe.style.marginBottom = "7px";
  iframe.style.border = "none";
  iframe.style.overflow = "hidden";
  iframe.style.display = "block";
  iframe.style.borderRadius = "8px";
  iframe.style.boxShadow = "0 7px 6px 1px rgb(0 0 0 / 16%)";
  iframe.style.backgroundColor = "white";
  iframe.style.display = "none";
};

window.onresize = () => {
  fixCSS();
};

window.onmessage = (message) => {
  message.data == "welcome_screen" && (close.innerHTML = CLOSE_ICON_DARK);
  message.data == "home_screen" && (close.innerHTML = CLOSE_ICON);
};

const setText = () => {
  bottomInfo.innerHTML =
    lang == "en"
      ? `Hi, I am <span style="color: #3061a3;"><b>Chetna</b></span>, your <span style="color: #3061a3;">AI Assistant</span>.`
      : `नमस्ते, मैं <span style="color: #3061a3;"><b>चेतना</b></span> हूँ, आपकी <span style="color: #3061a3;">एआई असिस्टेंट</span>।`;
  hoverInfo.innerHTML =
    lang == "en"
      ? `<span>Got a question? Ask <span style="color: #3061a3;"><b>CHETNA</b></span>...</span>`
      : `<span>कोई सवाल है? <span style="color: #3061a3;"><b>चेतना</b></span> से पूँछें...</span>`;
};

setInterval(() => {
  lang = localStorage.getItem("lang") ?? "en";
  setText();
}, 1000);

const onHover = () => {
  hoverInfo.style.display = "block";
};

const onHoverLeave = () => {
  hoverInfo.style.display = "none";
};

const openBot = () => {
  isOpen = true;
  iframe.src = "https://chatbot.delhimetrorail.com/#widget";
  fixCSS();
};

(() => {
  setIframe();
  launcher.style.cssText = LAUNCHER_CSS;
  hoverInfo.style.cssText = HOVER_CSS;
  bottomInfo.style.cssText = BOTTOM_LABEL_CSS;
  setText();
  mainDiv.id = "dmrc-chatbot-main";
  mainDiv.style.cssText = INIT_CSS;
  close.innerHTML = CLOSE_ICON;
  close.style.width = "2vw";
  close.style.height = "2vw";
  close.style.position = "absolute";
  close.style.top = "14px";
  close.style.right = "14px";
  close.style.cursor = "pointer";
  close.style.display = "none";
  close.style.textAlign = "end";

  close.onclick = () => {
    isOpen = false;
    fixCSS();
  };

  const image = document.createElement("img");
  image.src = LOGO_URL;
  image.style.width = "80%";
  image.style.borderRadius = "50%";

  launcher.appendChild(image);

  launcher.onclick = openBot;
  bottomInfo.onclick = openBot;

  launcher.onmouseover = onHover;
  launcher.onmouseleave = onHoverLeave;
  bottomInfo.onmouseover = onHover;
  bottomInfo.onmouseleave = onHoverLeave;

  mainDiv.appendChild(hoverInfo);
  mainDiv.appendChild(launcher);
  mainDiv.appendChild(bottomInfo);
  mainDiv.appendChild(iframe);
  mainDiv.appendChild(close);

  document.body.appendChild(mainDiv);
})();

// animation
document.head.insertAdjacentHTML("beforeend", ANIMATION_CSS);
setInterval(() => {
  if (!isOpen) {
    launcher.classList = ["shaker"];
    bottomInfo.classList = ["shaker"];
    setTimeout(() => {
      launcher.classList = [];
      bottomInfo.classList = [];
    }, 500);
  }
}, 3000);
