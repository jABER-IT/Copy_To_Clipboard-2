# Copy_To_Clipboard-2
Use Per > Code Tag And Copy Text

<!DOCTYPE html>
<html>
<head>

	<script src="https://cdn.jsdelivr.net/gh/jABER-IT/Html-CSS-JS-Host-File-Folder/Copy-To-Clipboard-Html-Css-Js-File/Copy.To.Clipboard.Finial.Code/run_prettify.js?lang=css&amp;skin=sunburst">
	</script>
	<style>
	   .K2_CBox {
	       position: relative;
	       background: #f9e8e8;
	       border-radius: 6px;
	       box-shadow: rgb(0 0 0 / 15%) 1.95px 1.95px 2.6px;
	       padding: 8px 8px 1px;
	       margin-bottom: 10px;
	   }

	   .K2_CBox .C_box_main {
	       cursor: pointer;
	       /* border-color: #f9e9e9; 
	   border: 2px solid #e12929; */
	       border-radius: 6px;
	       padding: 8px 10px 6px 10px;
	       position: absolute;
	       /* align-items: center; */
	       /* padding: 12px; */
	       outline: 0;
	       /* border: 0; */
	       border-radius: 50%;
	       background: #004cbd;
	       transition: all .3s ease;
	       -webkit-transition: all .3s ease;
	       z-index: 1;
	       right: 20px;
	       top: 0px;
	       margin: 5px;
	       transition: .1s;
	   }

	   .C_box_main:hover {
	       opacity: .8
	   }

	   .C_box_main .CBox_icn {
	       flex-shrink: 0;
	       display: inline-block;
	       width: 18px;
	       height: 18px;
	       background-image: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' fill='none' stroke='%23fefefe' stroke-linecap='round' stroke-linejoin='round' stroke-width='1.5' viewBox='0 0 24 24'><rect x='5.54615' y='5.54615' width='16.45385' height='16.45385' rx='4'/><path d='M171.33311,181.3216v-8.45385a4,4,0,0,1,4-4H183.787' transform='translate(-169.33311 -166.86775)'/><\/svg>");
	       background-size: cover;
	       background-repeat: no-repeat;
	       background-position: center;
	   }

	   .C_box_main.copied {
	       background: #2dcda7;
	       /* border: 2px solid #ffffff; */

	   }

	   .C_box_main.copied .CBox_icn {
	       background-image: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' fill='none' stroke='%23fefefe' stroke-linecap='round' stroke-linejoin='round' stroke-width='1.5' viewBox='0 0 24 24'><path d='M22 11.07V12a10 10 0 1 1-5.93-9.14'/><polyline points='23 3 12 14 9 11'/><\/svg>");
	   }
	</style>
	<title></title>
</head>
<body>
	<div class="K2_CBox">
		<pre class="prettyprint lang-scm highlight" style="position:relative;padding: 0px 10px 0px 30px; background:#13052e;display:block;direction:ltr;unicode-bidi:bidi-override;color:#fff;word-break:normal;border:none;border-left:7px solid #F9BC00;width:100%;background-color:#13052e;border-radius:8px">
    <code style="font-size:14px;nt-family:sourccepro,Inconsolata,lucida cole,Terminal,courier new,Courier;line-height: 1.3;;white-space:pre-wrap">
    111111111111111
    body: "This is my notification",
    icon: "ICON_URL",
    image: "IMAGE_URL"
});

     </code></pre>
	</div>
	<div class="K2_CBox">
		<pre class="prettyprint lang-scm highlight" style="position:relative;padding: 10px 0px 10px 30px;background:#13052e;display:block;direction:ltr;unicode-bidi:bidi-override;color:#fff;word-break:normal;border:none;border-left:7px solid #F9BC00;width:100%;background-color:#13052e;border-radius:8px">
    <code style="font-size:14px;nt-family:sourccepro,Inconsolata,lucida cole,Terminal,courier new,Courier;line-height: 1.3;;white-space:pre-wrap">
   22222222222222
    body: "This is my notification",
    icon: "ICON_URL",
    image: "IMAGE_URL"
});

     </code></pre>
	</div>
	<div class="K2_CBox">
		<pre class="prettyprint lang-scm highlight" style="position:relative;padding: 10px 0px 10px 30px;background:#13052e;display:block;direction:ltr;unicode-bidi:bidi-override;color:#fff;word-break:normal;border:none;border-left:7px solid #F9BC00;width:100%;background-color:#13052e;border-radius:8px">
    <code style="font-size:14px;line-height: 1.3;white-space:pre-wrap">
333333333333333333
    body: "This is my notification",
    icon: "ICON_URL",
    image: "IMAGE_URL"
});

     </code></pre>
	</div>
	<div class="lNotf" id="LefttNotif"></div>
	<script>
	   const svgCopy = '<i class="CBox_icn"><\/i>'
	   const svgCheck = '<i class="CBox_icn copied"><\/i>'
	   const addCopyButtons = (clipboard) => {
	       document.querySelectorAll("pre > code").forEach((codeBlock) => {
	           // Create button DOM element
	           const button = document.createElement("button");
	           button.className = "C_box_main";
	           button.type = "button";
	           button.innerHTML = svgCopy;
	           button.addEventListener("click", () => {
	               clipboard.writeText(codeBlock.innerText).then(() => {
	                   button.classList.add("copied");
	                   document.getElementById("LefttNotif").innerHTML = "<span>Copied to Clipboard!<\/span>";
	                   setTimeout(() => {
	                       button.classList.remove("copied")
	                   }, 3e3);
	                   console.log('Text Copy');
	               }, (error) => (button.innerHTML = "Error"));
	           });
	           // Attach button to DOM (.highlight > button > pre > code)
	           const pre = codeBlock.parentNode;
	           pre.parentNode.insertBefore(button, pre);
	       });
	   };

	   if (navigator && navigator.clipboard) {
	       addCopyButtons(navigator.clipboard);
	   } else {
	       const script = document.createElement("script");
	       script.src = "https://cdnjs.cloudflare.com/ajax/libs/clipboard-polyfill/2.7.0/clipboard-polyfill.promise.js";
	       script.integrity = "sha256-waClS2re9NUbXRsryKoof+F9qc1gjjIhc2eT7ZbIv94=";
	       script.crossOrigin = "anonymous";
	       script.onload = () => addCopyButtons(clipboard);
	       document.body.appendChild(script);
	   }
	</script>
</body>
</html>
