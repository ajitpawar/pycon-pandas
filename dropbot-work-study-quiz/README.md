<!DOCTYPE html>
<html>
<head>

<meta charset="utf-8" />
<title>Toronto weather - Quiz</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>

<style type="text/css">
    .clearfix{*zoom:1}.clearfix:before,.clearfix:after{display:table;content:"";line-height:0}
.clearfix:after{clear:both}
.hide-text{font:0/0 a;color:transparent;text-shadow:none;background-color:transparent;border:0}
.input-block-level{display:block;width:100%;min-height:30px;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box}
article,aside,details,figcaption,figure,footer,header,hgroup,nav,section{display:block}
audio,canvas,video{display:inline-block;*display:inline;*zoom:1}
audio:not([controls]){display:none}
html{font-size:100%;-webkit-text-size-adjust:100%;-ms-text-size-adjust:100%}
a:focus{outline:thin dotted #333;outline:5px auto -webkit-focus-ring-color;outline-offset:-2px}
a:hover,a:active{outline:0}
sub,sup{position:relative;font-size:75%;line-height:0;vertical-align:baseline}
sup{top:-0.5em}
sub{bottom:-0.25em}
img{max-width:100%;width:auto\9;height:auto;vertical-align:middle;border:0;-ms-interpolation-mode:bicubic}
#map_canvas img,.google-maps img{max-width:none}
button,input,select,textarea{margin:0;font-size:100%;vertical-align:middle}
button,input{*overflow:visible;line-height:normal}
button::-moz-focus-inner,input::-moz-focus-inner{padding:0;border:0}
button,html input[type="button"],input[type="reset"],input[type="submit"]{-webkit-appearance:button;cursor:pointer}
label,select,button,input[type="button"],input[type="reset"],input[type="submit"],input[type="radio"],input[type="checkbox"]{cursor:pointer}
input[type="search"]{-webkit-box-sizing:content-box;-moz-box-sizing:content-box;box-sizing:content-box;-webkit-appearance:textfield}
input[type="search"]::-webkit-search-decoration,input[type="search"]::-webkit-search-cancel-button{-webkit-appearance:none}
textarea{overflow:auto;vertical-align:top}
@media print{*{text-shadow:none !important;color:#000 !important;background:transparent !important;box-shadow:none !important} a,a:visited{text-decoration:underline} a[href]:after{content:" (" attr(href) ")"} abbr[title]:after{content:" (" attr(title) ")"} .ir a:after,a[href^="javascript:"]:after,a[href^="#"]:after{content:""} pre,blockquote{border:1px solid #999;page-break-inside:avoid} thead{display:table-header-group} tr,img{page-break-inside:avoid} img{max-width:100% !important} @page {margin:.5cm}p,h2,h3{orphans:3;widows:3} h2,h3{page-break-after:avoid}}body{margin:0;font-family:"Helvetica Neue",Helvetica,Arial,sans-serif;font-size:13px;line-height:20px;color:#000;background-color:#fff}
a{color:#08c;text-decoration:none}
a:hover,a:focus{color:#005580;text-decoration:underline}
.img-rounded{border-radius:6px;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px}
.img-polaroid{padding:4px;background-color:#fff;border:1px solid #ccc;border:1px solid rgba(0,0,0,0.2);-webkit-box-shadow:0 1px 3px rgba(0,0,0,0.1);-moz-box-shadow:0 1px 3px rgba(0,0,0,0.1);box-shadow:0 1px 3px rgba(0,0,0,0.1)}
.img-circle{border-radius:500px;-webkit-border-radius:500px;-moz-border-radius:500px;border-radius:500px}
.row{margin-left:-20px;*zoom:1}.row:before,.row:after{display:table;content:"";line-height:0}
.row:after{clear:both}
[class*="span"]{float:left;min-height:1px;margin-left:20px}
.container,.navbar-static-top .container,.navbar-fixed-top .container,.navbar-fixed-bottom .container{width:940px}
.span12{width:940px}
.span11{width:860px}
.span10{width:780px}
.span9{width:700px}
.span8{width:620px}
.span7{width:540px}
.span6{width:460px}
.span5{width:380px}
.span4{width:300px}
.span3{width:220px}
.span2{width:140px}
.span1{width:60px}
.offset12{margin-left:980px}
.offset11{margin-left:900px}
.offset10{margin-left:820px}
.offset9{margin-left:740px}
.offset8{margin-left:660px}
.offset7{margin-left:580px}
.offset6{margin-left:500px}
.offset5{margin-left:420px}
.offset4{margin-left:340px}
.offset3{margin-left:260px}
.offset2{margin-left:180px}
.offset1{margin-left:100px}
.row-fluid{width:100%;*zoom:1}.row-fluid:before,.row-fluid:after{display:table;content:"";line-height:0}
.row-fluid:after{clear:both}
.row-fluid [class*="span"]{display:block;width:100%;min-height:30px;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box;float:left;margin-left:2.127659574468085%;*margin-left:2.074468085106383%}
.row-fluid [class*="span"]:first-child{margin-left:0}
.row-fluid .controls-row [class*="span"]+[class*="span"]{margin-left:2.127659574468085%}
.row-fluid .span12{width:100%;*width:99.94680851063829%}
.row-fluid .span11{width:91.48936170212765%;*width:91.43617021276594%}
.row-fluid .span10{width:82.97872340425532%;*width:82.92553191489361%}
.row-fluid .span9{width:74.46808510638297%;*width:74.41489361702126%}
.row-fluid .span8{width:65.95744680851064%;*width:65.90425531914893%}
.row-fluid .span7{width:57.44680851063829%;*width:57.39361702127659%}
.row-fluid .span6{width:48.93617021276595%;*width:48.88297872340425%}
.row-fluid .span5{width:40.42553191489362%;*width:40.37234042553192%}
.row-fluid .span4{width:31.914893617021278%;*width:31.861702127659576%}
.row-fluid .span3{width:23.404255319148934%;*width:23.351063829787233%}
.row-fluid .span2{width:14.893617021276595%;*width:14.840425531914894%}
.row-fluid .span1{width:6.382978723404255%;*width:6.329787234042553%}
.row-fluid .offset12{margin-left:104.25531914893617%;*margin-left:104.14893617021275%}
.row-fluid .offset12:first-child{margin-left:102.12765957446808%;*margin-left:102.02127659574467%}
.row-fluid .offset11{margin-left:95.74468085106382%;*margin-left:95.6382978723404%}
.row-fluid .offset11:first-child{margin-left:93.61702127659574%;*margin-left:93.51063829787232%}
.row-fluid .offset10{margin-left:87.23404255319149%;*margin-left:87.12765957446807%}
.row-fluid .offset10:first-child{margin-left:85.1063829787234%;*margin-left:84.99999999999999%}
.row-fluid .offset9{margin-left:78.72340425531914%;*margin-left:78.61702127659572%}
.row-fluid .offset9:first-child{margin-left:76.59574468085106%;*margin-left:76.48936170212764%}
.row-fluid .offset8{margin-left:70.2127659574468%;*margin-left:70.10638297872339%}
.row-fluid .offset8:first-child{margin-left:68.08510638297872%;*margin-left:67.9787234042553%}
.row-fluid .offset7{margin-left:61.70212765957446%;*margin-left:61.59574468085106%}
.row-fluid .offset7:first-child{margin-left:59.574468085106375%;*margin-left:59.46808510638297%}
.row-fluid .offset6{margin-left:53.191489361702125%;*margin-left:53.085106382978715%}
.row-fluid .offset6:first-child{margin-left:51.063829787234035%;*margin-left:50.95744680851063%}
.row-fluid .offset5{margin-left:44.68085106382979%;*margin-left:44.57446808510638%}
.row-fluid .offset5:first-child{margin-left:42.5531914893617%;*margin-left:42.4468085106383%}
.row-fluid .offset4{margin-left:36.170212765957444%;*margin-left:36.06382978723405%}
.row-fluid .offset4:first-child{margin-left:34.04255319148936%;*margin-left:33.93617021276596%}
.row-fluid .offset3{margin-left:27.659574468085104%;*margin-left:27.5531914893617%}
.row-fluid .offset3:first-child{margin-left:25.53191489361702%;*margin-left:25.425531914893618%}
.row-fluid .offset2{margin-left:19.148936170212764%;*margin-left:19.04255319148936%}
.row-fluid .offset2:first-child{margin-left:17.02127659574468%;*margin-left:16.914893617021278%}
.row-fluid .offset1{margin-left:10.638297872340425%;*margin-left:10.53191489361702%}
.row-fluid .offset1:first-child{margin-left:8.51063829787234%;*margin-left:8.404255319148938%}
[class*="span"].hide,.row-fluid [class*="span"].hide{display:none}
[class*="span"].pull-right,.row-fluid [class*="span"].pull-right{float:right}
.container{margin-right:auto;margin-left:auto;*zoom:1}.container:before,.container:after{display:table;content:"";line-height:0}
.container:after{clear:both}
.container-fluid{padding-right:20px;padding-left:20px;*zoom:1}.container-fluid:before,.container-fluid:after{display:table;content:"";line-height:0}
.container-fluid:after{clear:both}
p{margin:0 0 10px}
.lead{margin-bottom:20px;font-size:19.5px;font-weight:200;line-height:30px}
small{font-size:85%}
strong{font-weight:bold}
em{font-style:italic}
cite{font-style:normal}
.muted{color:#999}
a.muted:hover,a.muted:focus{color:#808080}
.text-warning{color:#c09853}
a.text-warning:hover,a.text-warning:focus{color:#a47e3c}
.text-error{color:#b94a48}
a.text-error:hover,a.text-error:focus{color:#953b39}
.text-info{color:#3a87ad}
a.text-info:hover,a.text-info:focus{color:#2d6987}
.text-success{color:#468847}
a.text-success:hover,a.text-success:focus{color:#356635}
.text-left{text-align:left}
.text-right{text-align:right}
.text-center{text-align:center}
h1,h2,h3,h4,h5,h6{margin:10px 0;font-family:inherit;font-weight:bold;line-height:20px;color:inherit;text-rendering:optimizelegibility}h1 small,h2 small,h3 small,h4 small,h5 small,h6 small{font-weight:normal;line-height:1;color:#999}
h1,h2,h3{line-height:40px}
h1{font-size:35.75px}
h2{font-size:29.25px}
h3{font-size:22.75px}
h4{font-size:16.25px}
h5{font-size:13px}
h6{font-size:11.049999999999999px}
h1 small{font-size:22.75px}
h2 small{font-size:16.25px}
h3 small{font-size:13px}
h4 small{font-size:13px}
.page-header{padding-bottom:9px;margin:20px 0 30px;border-bottom:1px solid #eee}
ul,ol{padding:0;margin:0 0 10px 25px}
ul ul,ul ol,ol ol,ol ul{margin-bottom:0}
li{line-height:20px}
ul.unstyled,ol.unstyled{margin-left:0;list-style:none}
ul.inline,ol.inline{margin-left:0;list-style:none}ul.inline>li,ol.inline>li{display:inline-block;*display:inline;*zoom:1;padding-left:5px;padding-right:5px}
dl{margin-bottom:20px}
dt,dd{line-height:20px}
dt{font-weight:bold}
dd{margin-left:10px}
.dl-horizontal{*zoom:1}.dl-horizontal:before,.dl-horizontal:after{display:table;content:"";line-height:0}
.dl-horizontal:after{clear:both}
.dl-horizontal dt{float:left;width:160px;clear:left;text-align:right;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.dl-horizontal dd{margin-left:180px}
hr{margin:20px 0;border:0;border-top:1px solid #eee;border-bottom:1px solid #fff}
abbr[title],abbr[data-original-title]{cursor:help;border-bottom:1px dotted #999}
abbr.initialism{font-size:90%;text-transform:uppercase}
blockquote{padding:0 0 0 15px;margin:0 0 20px;border-left:5px solid #eee}blockquote p{margin-bottom:0;font-size:16.25px;font-weight:300;line-height:1.25}
blockquote small{display:block;line-height:20px;color:#999}blockquote small:before{content:'\2014 \00A0'}
blockquote.pull-right{float:right;padding-right:15px;padding-left:0;border-right:5px solid #eee;border-left:0}blockquote.pull-right p,blockquote.pull-right small{text-align:right}
blockquote.pull-right small:before{content:''}
blockquote.pull-right small:after{content:'\00A0 \2014'}
q:before,q:after,blockquote:before,blockquote:after{content:""}
address{display:block;margin-bottom:20px;font-style:normal;line-height:20px}
code,pre{padding:0 3px 2px;font-family:monospace;font-size:11px;color:#333;border-radius:3px;-webkit-border-radius:3px;-moz-border-radius:3px;border-radius:3px}
code{padding:2px 4px;color:#d14;background-color:#f7f7f9;border:1px solid #e1e1e8;white-space:nowrap}
pre{display:block;padding:9.5px;margin:0 0 10px;font-size:12px;line-height:20px;word-break:break-all;word-wrap:break-word;white-space:pre;white-space:pre-wrap;background-color:#f5f5f5;border:1px solid #ccc;border:1px solid rgba(0,0,0,0.15);border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}pre.prettyprint{margin-bottom:20px}
pre code{padding:0;color:inherit;white-space:pre;white-space:pre-wrap;background-color:transparent;border:0}
.pre-scrollable{max-height:340px;overflow-y:scroll}
form{margin:0 0 20px}
fieldset{padding:0;margin:0;border:0}
legend{display:block;width:100%;padding:0;margin-bottom:20px;font-size:19.5px;line-height:40px;color:#333;border:0;border-bottom:1px solid #e5e5e5}legend small{font-size:15px;color:#999}
label,input,button,select,textarea{font-size:13px;font-weight:normal;line-height:20px}
input,button,select,textarea{font-family:"Helvetica Neue",Helvetica,Arial,sans-serif}
label{display:block;margin-bottom:5px}
select,textarea,input[type="text"],input[type="password"],input[type="datetime"],input[type="datetime-local"],input[type="date"],input[type="month"],input[type="time"],input[type="week"],input[type="number"],input[type="email"],input[type="url"],input[type="search"],input[type="tel"],input[type="color"],.uneditable-input{display:inline-block;height:20px;padding:4px 6px;margin-bottom:10px;font-size:13px;line-height:20px;color:#555;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px;vertical-align:middle}
input,textarea,.uneditable-input{width:206px}
textarea{height:auto}
textarea,input[type="text"],input[type="password"],input[type="datetime"],input[type="datetime-local"],input[type="date"],input[type="month"],input[type="time"],input[type="week"],input[type="number"],input[type="email"],input[type="url"],input[type="search"],input[type="tel"],input[type="color"],.uneditable-input{background-color:#fff;border:1px solid #ccc;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);-webkit-transition:border linear .2s, box-shadow linear .2s;-moz-transition:border linear .2s, box-shadow linear .2s;-o-transition:border linear .2s, box-shadow linear .2s;transition:border linear .2s, box-shadow linear .2s}textarea:focus,input[type="text"]:focus,input[type="password"]:focus,input[type="datetime"]:focus,input[type="datetime-local"]:focus,input[type="date"]:focus,input[type="month"]:focus,input[type="time"]:focus,input[type="week"]:focus,input[type="number"]:focus,input[type="email"]:focus,input[type="url"]:focus,input[type="search"]:focus,input[type="tel"]:focus,input[type="color"]:focus,.uneditable-input:focus{border-color:rgba(82,168,236,0.8);outline:0;outline:thin dotted \9;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(82,168,236,.6);-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(82,168,236,.6);box-shadow:inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(82,168,236,.6)}
input[type="radio"],input[type="checkbox"]{margin:4px 0 0;*margin-top:0;margin-top:1px \9;line-height:normal}
input[type="file"],input[type="image"],input[type="submit"],input[type="reset"],input[type="button"],input[type="radio"],input[type="checkbox"]{width:auto}
select,input[type="file"]{height:30px;*margin-top:4px;line-height:30px}
select{width:220px;border:1px solid #ccc;background-color:#fff}
select[multiple],select[size]{height:auto}
select:focus,input[type="file"]:focus,input[type="radio"]:focus,input[type="checkbox"]:focus{outline:thin dotted #333;outline:5px auto -webkit-focus-ring-color;outline-offset:-2px}
.uneditable-input,.uneditable-textarea{color:#999;background-color:#fcfcfc;border-color:#ccc;-webkit-box-shadow:inset 0 1px 2px rgba(0,0,0,0.025);-moz-box-shadow:inset 0 1px 2px rgba(0,0,0,0.025);box-shadow:inset 0 1px 2px rgba(0,0,0,0.025);cursor:not-allowed}
.uneditable-input{overflow:hidden;white-space:nowrap}
.uneditable-textarea{width:auto;height:auto}
input:-moz-placeholder,textarea:-moz-placeholder{color:#999}
input:-ms-input-placeholder,textarea:-ms-input-placeholder{color:#999}
input::-webkit-input-placeholder,textarea::-webkit-input-placeholder{color:#999}
.radio,.checkbox{min-height:20px;padding-left:20px}
.radio input[type="radio"],.checkbox input[type="checkbox"]{float:left;margin-left:-20px}
.controls>.radio:first-child,.controls>.checkbox:first-child{padding-top:5px}
.radio.inline,.checkbox.inline{display:inline-block;padding-top:5px;margin-bottom:0;vertical-align:middle}
.radio.inline+.radio.inline,.checkbox.inline+.checkbox.inline{margin-left:10px}
.input-mini{width:60px}
.input-small{width:90px}
.input-medium{width:150px}
.input-large{width:210px}
.input-xlarge{width:270px}
.input-xxlarge{width:530px}
input[class*="span"],select[class*="span"],textarea[class*="span"],.uneditable-input[class*="span"],.row-fluid input[class*="span"],.row-fluid select[class*="span"],.row-fluid textarea[class*="span"],.row-fluid .uneditable-input[class*="span"]{float:none;margin-left:0}
.input-append input[class*="span"],.input-append .uneditable-input[class*="span"],.input-prepend input[class*="span"],.input-prepend .uneditable-input[class*="span"],.row-fluid input[class*="span"],.row-fluid select[class*="span"],.row-fluid textarea[class*="span"],.row-fluid .uneditable-input[class*="span"],.row-fluid .input-prepend [class*="span"],.row-fluid .input-append [class*="span"]{display:inline-block}
input,textarea,.uneditable-input{margin-left:0}
.controls-row [class*="span"]+[class*="span"]{margin-left:20px}
input.span12,textarea.span12,.uneditable-input.span12{width:926px}
input.span11,textarea.span11,.uneditable-input.span11{width:846px}
input.span10,textarea.span10,.uneditable-input.span10{width:766px}
input.span9,textarea.span9,.uneditable-input.span9{width:686px}
input.span8,textarea.span8,.uneditable-input.span8{width:606px}
input.span7,textarea.span7,.uneditable-input.span7{width:526px}
input.span6,textarea.span6,.uneditable-input.span6{width:446px}
input.span5,textarea.span5,.uneditable-input.span5{width:366px}
input.span4,textarea.span4,.uneditable-input.span4{width:286px}
input.span3,textarea.span3,.uneditable-input.span3{width:206px}
input.span2,textarea.span2,.uneditable-input.span2{width:126px}
input.span1,textarea.span1,.uneditable-input.span1{width:46px}
.controls-row{*zoom:1}.controls-row:before,.controls-row:after{display:table;content:"";line-height:0}
.controls-row:after{clear:both}
.controls-row [class*="span"],.row-fluid .controls-row [class*="span"]{float:left}
.controls-row .checkbox[class*="span"],.controls-row .radio[class*="span"]{padding-top:5px}
input[disabled],select[disabled],textarea[disabled],input[readonly],select[readonly],textarea[readonly]{cursor:not-allowed;background-color:#eee}
input[type="radio"][disabled],input[type="checkbox"][disabled],input[type="radio"][readonly],input[type="checkbox"][readonly]{background-color:transparent}
.control-group.warning .control-label,.control-group.warning .help-block,.control-group.warning .help-inline{color:#c09853}
.control-group.warning .checkbox,.control-group.warning .radio,.control-group.warning input,.control-group.warning select,.control-group.warning textarea{color:#c09853}
.control-group.warning input,.control-group.warning select,.control-group.warning textarea{border-color:#c09853;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);box-shadow:inset 0 1px 1px rgba(0,0,0,0.075)}.control-group.warning input:focus,.control-group.warning select:focus,.control-group.warning textarea:focus{border-color:#a47e3c;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #dbc59e;-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #dbc59e;box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #dbc59e}
.control-group.warning .input-prepend .add-on,.control-group.warning .input-append .add-on{color:#c09853;background-color:#fcf8e3;border-color:#c09853}
.control-group.error .control-label,.control-group.error .help-block,.control-group.error .help-inline{color:#b94a48}
.control-group.error .checkbox,.control-group.error .radio,.control-group.error input,.control-group.error select,.control-group.error textarea{color:#b94a48}
.control-group.error input,.control-group.error select,.control-group.error textarea{border-color:#b94a48;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);box-shadow:inset 0 1px 1px rgba(0,0,0,0.075)}.control-group.error input:focus,.control-group.error select:focus,.control-group.error textarea:focus{border-color:#953b39;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #d59392;-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #d59392;box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #d59392}
.control-group.error .input-prepend .add-on,.control-group.error .input-append .add-on{color:#b94a48;background-color:#f2dede;border-color:#b94a48}
.control-group.success .control-label,.control-group.success .help-block,.control-group.success .help-inline{color:#468847}
.control-group.success .checkbox,.control-group.success .radio,.control-group.success input,.control-group.success select,.control-group.success textarea{color:#468847}
.control-group.success input,.control-group.success select,.control-group.success textarea{border-color:#468847;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);box-shadow:inset 0 1px 1px rgba(0,0,0,0.075)}.control-group.success input:focus,.control-group.success select:focus,.control-group.success textarea:focus{border-color:#356635;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #7aba7b;-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #7aba7b;box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #7aba7b}
.control-group.success .input-prepend .add-on,.control-group.success .input-append .add-on{color:#468847;background-color:#dff0d8;border-color:#468847}
.control-group.info .control-label,.control-group.info .help-block,.control-group.info .help-inline{color:#3a87ad}
.control-group.info .checkbox,.control-group.info .radio,.control-group.info input,.control-group.info select,.control-group.info textarea{color:#3a87ad}
.control-group.info input,.control-group.info select,.control-group.info textarea{border-color:#3a87ad;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075);box-shadow:inset 0 1px 1px rgba(0,0,0,0.075)}.control-group.info input:focus,.control-group.info select:focus,.control-group.info textarea:focus{border-color:#2d6987;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #7ab5d3;-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #7ab5d3;box-shadow:inset 0 1px 1px rgba(0,0,0,0.075),0 0 6px #7ab5d3}
.control-group.info .input-prepend .add-on,.control-group.info .input-append .add-on{color:#3a87ad;background-color:#d9edf7;border-color:#3a87ad}
input:focus:invalid,textarea:focus:invalid,select:focus:invalid{color:#b94a48;border-color:#ee5f5b}input:focus:invalid:focus,textarea:focus:invalid:focus,select:focus:invalid:focus{border-color:#e9322d;-webkit-box-shadow:0 0 6px #f8b9b7;-moz-box-shadow:0 0 6px #f8b9b7;box-shadow:0 0 6px #f8b9b7}
.form-actions{padding:19px 20px 20px;margin-top:20px;margin-bottom:20px;background-color:#f5f5f5;border-top:1px solid #e5e5e5;*zoom:1}.form-actions:before,.form-actions:after{display:table;content:"";line-height:0}
.form-actions:after{clear:both}
.help-block,.help-inline{color:#262626}
.help-block{display:block;margin-bottom:10px}
.help-inline{display:inline-block;*display:inline;*zoom:1;vertical-align:middle;padding-left:5px}
.input-append,.input-prepend{display:inline-block;margin-bottom:10px;vertical-align:middle;font-size:0;white-space:nowrap}.input-append input,.input-prepend input,.input-append select,.input-prepend select,.input-append .uneditable-input,.input-prepend .uneditable-input,.input-append .dropdown-menu,.input-prepend .dropdown-menu,.input-append .popover,.input-prepend .popover{font-size:13px}
.input-append input,.input-prepend input,.input-append select,.input-prepend select,.input-append .uneditable-input,.input-prepend .uneditable-input{position:relative;margin-bottom:0;*margin-left:0;vertical-align:top;border-radius:0 4px 4px 0;-webkit-border-radius:0 4px 4px 0;-moz-border-radius:0 4px 4px 0;border-radius:0 4px 4px 0}.input-append input:focus,.input-prepend input:focus,.input-append select:focus,.input-prepend select:focus,.input-append .uneditable-input:focus,.input-prepend .uneditable-input:focus{z-index:2}
.input-append .add-on,.input-prepend .add-on{display:inline-block;width:auto;height:20px;min-width:16px;padding:4px 5px;font-size:13px;font-weight:normal;line-height:20px;text-align:center;text-shadow:0 1px 0 #fff;background-color:#eee;border:1px solid #ccc}
.input-append .add-on,.input-prepend .add-on,.input-append .btn,.input-prepend .btn,.input-append .btn-group>.dropdown-toggle,.input-prepend .btn-group>.dropdown-toggle{vertical-align:top;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.input-append .active,.input-prepend .active{background-color:#a9dba9;border-color:#46a546}
.input-prepend .add-on,.input-prepend .btn{margin-right:-1px}
.input-prepend .add-on:first-child,.input-prepend .btn:first-child{border-radius:4px 0 0 4px;-webkit-border-radius:4px 0 0 4px;-moz-border-radius:4px 0 0 4px;border-radius:4px 0 0 4px}
.input-append input,.input-append select,.input-append .uneditable-input{border-radius:4px 0 0 4px;-webkit-border-radius:4px 0 0 4px;-moz-border-radius:4px 0 0 4px;border-radius:4px 0 0 4px}.input-append input+.btn-group .btn:last-child,.input-append select+.btn-group .btn:last-child,.input-append .uneditable-input+.btn-group .btn:last-child{border-radius:0 4px 4px 0;-webkit-border-radius:0 4px 4px 0;-moz-border-radius:0 4px 4px 0;border-radius:0 4px 4px 0}
.input-append .add-on,.input-append .btn,.input-append .btn-group{margin-left:-1px}
.input-append .add-on:last-child,.input-append .btn:last-child,.input-append .btn-group:last-child>.dropdown-toggle{border-radius:0 4px 4px 0;-webkit-border-radius:0 4px 4px 0;-moz-border-radius:0 4px 4px 0;border-radius:0 4px 4px 0}
.input-prepend.input-append input,.input-prepend.input-append select,.input-prepend.input-append .uneditable-input{border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}.input-prepend.input-append input+.btn-group .btn,.input-prepend.input-append select+.btn-group .btn,.input-prepend.input-append .uneditable-input+.btn-group .btn{border-radius:0 4px 4px 0;-webkit-border-radius:0 4px 4px 0;-moz-border-radius:0 4px 4px 0;border-radius:0 4px 4px 0}
.input-prepend.input-append .add-on:first-child,.input-prepend.input-append .btn:first-child{margin-right:-1px;border-radius:4px 0 0 4px;-webkit-border-radius:4px 0 0 4px;-moz-border-radius:4px 0 0 4px;border-radius:4px 0 0 4px}
.input-prepend.input-append .add-on:last-child,.input-prepend.input-append .btn:last-child{margin-left:-1px;border-radius:0 4px 4px 0;-webkit-border-radius:0 4px 4px 0;-moz-border-radius:0 4px 4px 0;border-radius:0 4px 4px 0}
.input-prepend.input-append .btn-group:first-child{margin-left:0}
input.search-query{padding-right:14px;padding-right:4px \9;padding-left:14px;padding-left:4px \9;margin-bottom:0;border-radius:15px;-webkit-border-radius:15px;-moz-border-radius:15px;border-radius:15px}
.form-search .input-append .search-query,.form-search .input-prepend .search-query{border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.form-search .input-append .search-query{border-radius:14px 0 0 14px;-webkit-border-radius:14px 0 0 14px;-moz-border-radius:14px 0 0 14px;border-radius:14px 0 0 14px}
.form-search .input-append .btn{border-radius:0 14px 14px 0;-webkit-border-radius:0 14px 14px 0;-moz-border-radius:0 14px 14px 0;border-radius:0 14px 14px 0}
.form-search .input-prepend .search-query{border-radius:0 14px 14px 0;-webkit-border-radius:0 14px 14px 0;-moz-border-radius:0 14px 14px 0;border-radius:0 14px 14px 0}
.form-search .input-prepend .btn{border-radius:14px 0 0 14px;-webkit-border-radius:14px 0 0 14px;-moz-border-radius:14px 0 0 14px;border-radius:14px 0 0 14px}
.form-search input,.form-inline input,.form-horizontal input,.form-search textarea,.form-inline textarea,.form-horizontal textarea,.form-search select,.form-inline select,.form-horizontal select,.form-search .help-inline,.form-inline .help-inline,.form-horizontal .help-inline,.form-search .uneditable-input,.form-inline .uneditable-input,.form-horizontal .uneditable-input,.form-search .input-prepend,.form-inline .input-prepend,.form-horizontal .input-prepend,.form-search .input-append,.form-inline .input-append,.form-horizontal .input-append{display:inline-block;*display:inline;*zoom:1;margin-bottom:0;vertical-align:middle}
.form-search .hide,.form-inline .hide,.form-horizontal .hide{display:none}
.form-search label,.form-inline label,.form-search .btn-group,.form-inline .btn-group{display:inline-block}
.form-search .input-append,.form-inline .input-append,.form-search .input-prepend,.form-inline .input-prepend{margin-bottom:0}
.form-search .radio,.form-search .checkbox,.form-inline .radio,.form-inline .checkbox{padding-left:0;margin-bottom:0;vertical-align:middle}
.form-search .radio input[type="radio"],.form-search .checkbox input[type="checkbox"],.form-inline .radio input[type="radio"],.form-inline .checkbox input[type="checkbox"]{float:left;margin-right:3px;margin-left:0}
.control-group{margin-bottom:10px}
legend+.control-group{margin-top:20px;-webkit-margin-top-collapse:separate}
.form-horizontal .control-group{margin-bottom:20px;*zoom:1}.form-horizontal .control-group:before,.form-horizontal .control-group:after{display:table;content:"";line-height:0}
.form-horizontal .control-group:after{clear:both}
.form-horizontal .control-label{float:left;width:160px;padding-top:5px;text-align:right}
.form-horizontal .controls{*display:inline-block;*padding-left:20px;margin-left:180px;*margin-left:0}.form-horizontal .controls:first-child{*padding-left:180px}
.form-horizontal .help-block{margin-bottom:0}
.form-horizontal input+.help-block,.form-horizontal select+.help-block,.form-horizontal textarea+.help-block,.form-horizontal .uneditable-input+.help-block,.form-horizontal .input-prepend+.help-block,.form-horizontal .input-append+.help-block{margin-top:10px}
.form-horizontal .form-actions{padding-left:180px}
table{max-width:100%;background-color:transparent;border-collapse:collapse;border-spacing:0}
.table{width:100%;margin-bottom:20px}.table th,.table td{padding:8px;line-height:20px;text-align:left;vertical-align:top;border-top:1px solid #ddd}
.table th{font-weight:bold}
.table thead th{vertical-align:bottom}
.table caption+thead tr:first-child th,.table caption+thead tr:first-child td,.table colgroup+thead tr:first-child th,.table colgroup+thead tr:first-child td,.table thead:first-child tr:first-child th,.table thead:first-child tr:first-child td{border-top:0}
.table tbody+tbody{border-top:2px solid #ddd}
.table .table{background-color:#fff}
.table-condensed th,.table-condensed td{padding:4px 5px}
.table-bordered{border:1px solid #ddd;border-collapse:separate;*border-collapse:collapse;border-left:0;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}.table-bordered th,.table-bordered td{border-left:1px solid #ddd}
.table-bordered caption+thead tr:first-child th,.table-bordered caption+tbody tr:first-child th,.table-bordered caption+tbody tr:first-child td,.table-bordered colgroup+thead tr:first-child th,.table-bordered colgroup+tbody tr:first-child th,.table-bordered colgroup+tbody tr:first-child td,.table-bordered thead:first-child tr:first-child th,.table-bordered tbody:first-child tr:first-child th,.table-bordered tbody:first-child tr:first-child td{border-top:0}
.table-bordered thead:first-child tr:first-child>th:first-child,.table-bordered tbody:first-child tr:first-child>td:first-child,.table-bordered tbody:first-child tr:first-child>th:first-child{-webkit-border-top-left-radius:4px;-moz-border-radius-topleft:4px;border-top-left-radius:4px}
.table-bordered thead:first-child tr:first-child>th:last-child,.table-bordered tbody:first-child tr:first-child>td:last-child,.table-bordered tbody:first-child tr:first-child>th:last-child{-webkit-border-top-right-radius:4px;-moz-border-radius-topright:4px;border-top-right-radius:4px}
.table-bordered thead:last-child tr:last-child>th:first-child,.table-bordered tbody:last-child tr:last-child>td:first-child,.table-bordered tbody:last-child tr:last-child>th:first-child,.table-bordered tfoot:last-child tr:last-child>td:first-child,.table-bordered tfoot:last-child tr:last-child>th:first-child{-webkit-border-bottom-left-radius:4px;-moz-border-radius-bottomleft:4px;border-bottom-left-radius:4px}
.table-bordered thead:last-child tr:last-child>th:last-child,.table-bordered tbody:last-child tr:last-child>td:last-child,.table-bordered tbody:last-child tr:last-child>th:last-child,.table-bordered tfoot:last-child tr:last-child>td:last-child,.table-bordered tfoot:last-child tr:last-child>th:last-child{-webkit-border-bottom-right-radius:4px;-moz-border-radius-bottomright:4px;border-bottom-right-radius:4px}
.table-bordered tfoot+tbody:last-child tr:last-child td:first-child{-webkit-border-bottom-left-radius:0;-moz-border-radius-bottomleft:0;border-bottom-left-radius:0}
.table-bordered tfoot+tbody:last-child tr:last-child td:last-child{-webkit-border-bottom-right-radius:0;-moz-border-radius-bottomright:0;border-bottom-right-radius:0}
.table-bordered caption+thead tr:first-child th:first-child,.table-bordered caption+tbody tr:first-child td:first-child,.table-bordered colgroup+thead tr:first-child th:first-child,.table-bordered colgroup+tbody tr:first-child td:first-child{-webkit-border-top-left-radius:4px;-moz-border-radius-topleft:4px;border-top-left-radius:4px}
.table-bordered caption+thead tr:first-child th:last-child,.table-bordered caption+tbody tr:first-child td:last-child,.table-bordered colgroup+thead tr:first-child th:last-child,.table-bordered colgroup+tbody tr:first-child td:last-child{-webkit-border-top-right-radius:4px;-moz-border-radius-topright:4px;border-top-right-radius:4px}
.table-striped tbody>tr:nth-child(odd)>td,.table-striped tbody>tr:nth-child(odd)>th{background-color:#f9f9f9}
.table-hover tbody tr:hover>td,.table-hover tbody tr:hover>th{background-color:#f5f5f5}
table td[class*="span"],table th[class*="span"],.row-fluid table td[class*="span"],.row-fluid table th[class*="span"]{display:table-cell;float:none;margin-left:0}
.table td.span1,.table th.span1{float:none;width:44px;margin-left:0}
.table td.span2,.table th.span2{float:none;width:124px;margin-left:0}
.table td.span3,.table th.span3{float:none;width:204px;margin-left:0}
.table td.span4,.table th.span4{float:none;width:284px;margin-left:0}
.table td.span5,.table th.span5{float:none;width:364px;margin-left:0}
.table td.span6,.table th.span6{float:none;width:444px;margin-left:0}
.table td.span7,.table th.span7{float:none;width:524px;margin-left:0}
.table td.span8,.table th.span8{float:none;width:604px;margin-left:0}
.table td.span9,.table th.span9{float:none;width:684px;margin-left:0}
.table td.span10,.table th.span10{float:none;width:764px;margin-left:0}
.table td.span11,.table th.span11{float:none;width:844px;margin-left:0}
.table td.span12,.table th.span12{float:none;width:924px;margin-left:0}
.table tbody tr.success>td{background-color:#dff0d8}
.table tbody tr.error>td{background-color:#f2dede}
.table tbody tr.warning>td{background-color:#fcf8e3}
.table tbody tr.info>td{background-color:#d9edf7}
.table-hover tbody tr.success:hover>td{background-color:#d0e9c6}
.table-hover tbody tr.error:hover>td{background-color:#ebcccc}
.table-hover tbody tr.warning:hover>td{background-color:#faf2cc}
.table-hover tbody tr.info:hover>td{background-color:#c4e3f3}
[class^="icon-"],[class*=" icon-"]{display:inline-block;width:14px;height:14px;*margin-right:.3em;line-height:14px;vertical-align:text-top;background-image:url("../img/glyphicons-halflings.png");background-position:14px 14px;background-repeat:no-repeat;margin-top:1px}
.icon-white,.nav-pills>.active>a>[class^="icon-"],.nav-pills>.active>a>[class*=" icon-"],.nav-list>.active>a>[class^="icon-"],.nav-list>.active>a>[class*=" icon-"],.navbar-inverse .nav>.active>a>[class^="icon-"],.navbar-inverse .nav>.active>a>[class*=" icon-"],.dropdown-menu>li>a:hover>[class^="icon-"],.dropdown-menu>li>a:focus>[class^="icon-"],.dropdown-menu>li>a:hover>[class*=" icon-"],.dropdown-menu>li>a:focus>[class*=" icon-"],.dropdown-menu>.active>a>[class^="icon-"],.dropdown-menu>.active>a>[class*=" icon-"],.dropdown-submenu:hover>a>[class^="icon-"],.dropdown-submenu:focus>a>[class^="icon-"],.dropdown-submenu:hover>a>[class*=" icon-"],.dropdown-submenu:focus>a>[class*=" icon-"]{background-image:url("../img/glyphicons-halflings-white.png")}
.icon-glass{background-position:0 0}
.icon-music{background-position:-24px 0}
.icon-search{background-position:-48px 0}
.icon-envelope{background-position:-72px 0}
.icon-heart{background-position:-96px 0}
.icon-star{background-position:-120px 0}
.icon-star-empty{background-position:-144px 0}
.icon-user{background-position:-168px 0}
.icon-film{background-position:-192px 0}
.icon-th-large{background-position:-216px 0}
.icon-th{background-position:-240px 0}
.icon-th-list{background-position:-264px 0}
.icon-ok{background-position:-288px 0}
.icon-remove{background-position:-312px 0}
.icon-zoom-in{background-position:-336px 0}
.icon-zoom-out{background-position:-360px 0}
.icon-off{background-position:-384px 0}
.icon-signal{background-position:-408px 0}
.icon-cog{background-position:-432px 0}
.icon-trash{background-position:-456px 0}
.icon-home{background-position:0 -24px}
.icon-file{background-position:-24px -24px}
.icon-time{background-position:-48px -24px}
.icon-road{background-position:-72px -24px}
.icon-download-alt{background-position:-96px -24px}
.icon-download{background-position:-120px -24px}
.icon-upload{background-position:-144px -24px}
.icon-inbox{background-position:-168px -24px}
.icon-play-circle{background-position:-192px -24px}
.icon-repeat{background-position:-216px -24px}
.icon-refresh{background-position:-240px -24px}
.icon-list-alt{background-position:-264px -24px}
.icon-lock{background-position:-287px -24px}
.icon-flag{background-position:-312px -24px}
.icon-headphones{background-position:-336px -24px}
.icon-volume-off{background-position:-360px -24px}
.icon-volume-down{background-position:-384px -24px}
.icon-volume-up{background-position:-408px -24px}
.icon-qrcode{background-position:-432px -24px}
.icon-barcode{background-position:-456px -24px}
.icon-tag{background-position:0 -48px}
.icon-tags{background-position:-25px -48px}
.icon-book{background-position:-48px -48px}
.icon-bookmark{background-position:-72px -48px}
.icon-print{background-position:-96px -48px}
.icon-camera{background-position:-120px -48px}
.icon-font{background-position:-144px -48px}
.icon-bold{background-position:-167px -48px}
.icon-italic{background-position:-192px -48px}
.icon-text-height{background-position:-216px -48px}
.icon-text-width{background-position:-240px -48px}
.icon-align-left{background-position:-264px -48px}
.icon-align-center{background-position:-288px -48px}
.icon-align-right{background-position:-312px -48px}
.icon-align-justify{background-position:-336px -48px}
.icon-list{background-position:-360px -48px}
.icon-indent-left{background-position:-384px -48px}
.icon-indent-right{background-position:-408px -48px}
.icon-facetime-video{background-position:-432px -48px}
.icon-picture{background-position:-456px -48px}
.icon-pencil{background-position:0 -72px}
.icon-map-marker{background-position:-24px -72px}
.icon-adjust{background-position:-48px -72px}
.icon-tint{background-position:-72px -72px}
.icon-edit{background-position:-96px -72px}
.icon-share{background-position:-120px -72px}
.icon-check{background-position:-144px -72px}
.icon-move{background-position:-168px -72px}
.icon-step-backward{background-position:-192px -72px}
.icon-fast-backward{background-position:-216px -72px}
.icon-backward{background-position:-240px -72px}
.icon-play{background-position:-264px -72px}
.icon-pause{background-position:-288px -72px}
.icon-stop{background-position:-312px -72px}
.icon-forward{background-position:-336px -72px}
.icon-fast-forward{background-position:-360px -72px}
.icon-step-forward{background-position:-384px -72px}
.icon-eject{background-position:-408px -72px}
.icon-chevron-left{background-position:-432px -72px}
.icon-chevron-right{background-position:-456px -72px}
.icon-plus-sign{background-position:0 -96px}
.icon-minus-sign{background-position:-24px -96px}
.icon-remove-sign{background-position:-48px -96px}
.icon-ok-sign{background-position:-72px -96px}
.icon-question-sign{background-position:-96px -96px}
.icon-info-sign{background-position:-120px -96px}
.icon-screenshot{background-position:-144px -96px}
.icon-remove-circle{background-position:-168px -96px}
.icon-ok-circle{background-position:-192px -96px}
.icon-ban-circle{background-position:-216px -96px}
.icon-arrow-left{background-position:-240px -96px}
.icon-arrow-right{background-position:-264px -96px}
.icon-arrow-up{background-position:-289px -96px}
.icon-arrow-down{background-position:-312px -96px}
.icon-share-alt{background-position:-336px -96px}
.icon-resize-full{background-position:-360px -96px}
.icon-resize-small{background-position:-384px -96px}
.icon-plus{background-position:-408px -96px}
.icon-minus{background-position:-433px -96px}
.icon-asterisk{background-position:-456px -96px}
.icon-exclamation-sign{background-position:0 -120px}
.icon-gift{background-position:-24px -120px}
.icon-leaf{background-position:-48px -120px}
.icon-fire{background-position:-72px -120px}
.icon-eye-open{background-position:-96px -120px}
.icon-eye-close{background-position:-120px -120px}
.icon-warning-sign{background-position:-144px -120px}
.icon-plane{background-position:-168px -120px}
.icon-calendar{background-position:-192px -120px}
.icon-random{background-position:-216px -120px;width:16px}
.icon-comment{background-position:-240px -120px}
.icon-magnet{background-position:-264px -120px}
.icon-chevron-up{background-position:-288px -120px}
.icon-chevron-down{background-position:-313px -119px}
.icon-retweet{background-position:-336px -120px}
.icon-shopping-cart{background-position:-360px -120px}
.icon-folder-close{background-position:-384px -120px;width:16px}
.icon-folder-open{background-position:-408px -120px;width:16px}
.icon-resize-vertical{background-position:-432px -119px}
.icon-resize-horizontal{background-position:-456px -118px}
.icon-hdd{background-position:0 -144px}
.icon-bullhorn{background-position:-24px -144px}
.icon-bell{background-position:-48px -144px}
.icon-certificate{background-position:-72px -144px}
.icon-thumbs-up{background-position:-96px -144px}
.icon-thumbs-down{background-position:-120px -144px}
.icon-hand-right{background-position:-144px -144px}
.icon-hand-left{background-position:-168px -144px}
.icon-hand-up{background-position:-192px -144px}
.icon-hand-down{background-position:-216px -144px}
.icon-circle-arrow-right{background-position:-240px -144px}
.icon-circle-arrow-left{background-position:-264px -144px}
.icon-circle-arrow-up{background-position:-288px -144px}
.icon-circle-arrow-down{background-position:-312px -144px}
.icon-globe{background-position:-336px -144px}
.icon-wrench{background-position:-360px -144px}
.icon-tasks{background-position:-384px -144px}
.icon-filter{background-position:-408px -144px}
.icon-briefcase{background-position:-432px -144px}
.icon-fullscreen{background-position:-456px -144px}
.dropup,.dropdown{position:relative}
.dropdown-toggle{*margin-bottom:-3px}
.dropdown-toggle:active,.open .dropdown-toggle{outline:0}
.caret{display:inline-block;width:0;height:0;vertical-align:top;border-top:4px solid #000;border-right:4px solid transparent;border-left:4px solid transparent;content:""}
.dropdown .caret{margin-top:8px;margin-left:2px}
.dropdown-menu{position:absolute;top:100%;left:0;z-index:1000;display:none;float:left;min-width:160px;padding:5px 0;margin:2px 0 0;list-style:none;background-color:#fff;border:1px solid #ccc;border:1px solid rgba(0,0,0,0.2);*border-right-width:2px;*border-bottom-width:2px;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px;-webkit-box-shadow:0 5px 10px rgba(0,0,0,0.2);-moz-box-shadow:0 5px 10px rgba(0,0,0,0.2);box-shadow:0 5px 10px rgba(0,0,0,0.2);-webkit-background-clip:padding-box;-moz-background-clip:padding;background-clip:padding-box}.dropdown-menu.pull-right{right:0;left:auto}
.dropdown-menu .divider{*width:100%;height:1px;margin:9px 1px;*margin:-5px 0 5px;overflow:hidden;background-color:#e5e5e5;border-bottom:1px solid #fff}
.dropdown-menu>li>a{display:block;padding:3px 20px;clear:both;font-weight:normal;line-height:20px;color:#333;white-space:nowrap}
.dropdown-menu>li>a:hover,.dropdown-menu>li>a:focus,.dropdown-submenu:hover>a,.dropdown-submenu:focus>a{text-decoration:none;color:#fff;background-color:#0081c2;background-image:-moz-linear-gradient(top, #08c, #0077b3);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#08c), to(#0077b3));background-image:-webkit-linear-gradient(top, #08c, #0077b3);background-image:-o-linear-gradient(top, #08c, #0077b3);background-image:linear-gradient(to bottom, #08c, #0077b3);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff0088cc', endColorstr='#ff0077b3', GradientType=0)}
.dropdown-menu>.active>a,.dropdown-menu>.active>a:hover,.dropdown-menu>.active>a:focus{color:#fff;text-decoration:none;outline:0;background-color:#0081c2;background-image:-moz-linear-gradient(top, #08c, #0077b3);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#08c), to(#0077b3));background-image:-webkit-linear-gradient(top, #08c, #0077b3);background-image:-o-linear-gradient(top, #08c, #0077b3);background-image:linear-gradient(to bottom, #08c, #0077b3);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff0088cc', endColorstr='#ff0077b3', GradientType=0)}
.dropdown-menu>.disabled>a,.dropdown-menu>.disabled>a:hover,.dropdown-menu>.disabled>a:focus{color:#999}
.dropdown-menu>.disabled>a:hover,.dropdown-menu>.disabled>a:focus{text-decoration:none;background-color:transparent;background-image:none;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false);cursor:default}
.open{*z-index:1000}.open>.dropdown-menu{display:block}
.dropdown-backdrop{position:fixed;left:0;right:0;bottom:0;top:0;z-index:990}
.pull-right>.dropdown-menu{right:0;left:auto}
.dropup .caret,.navbar-fixed-bottom .dropdown .caret{border-top:0;border-bottom:4px solid #000;content:""}
.dropup .dropdown-menu,.navbar-fixed-bottom .dropdown .dropdown-menu{top:auto;bottom:100%;margin-bottom:1px}
.dropdown-submenu{position:relative}
.dropdown-submenu>.dropdown-menu{top:0;left:100%;margin-top:-6px;margin-left:-1px;border-radius:0 6px 6px 6px;-webkit-border-radius:0 6px 6px 6px;-moz-border-radius:0 6px 6px 6px;border-radius:0 6px 6px 6px}
.dropdown-submenu:hover>.dropdown-menu{display:block}
.dropup .dropdown-submenu>.dropdown-menu{top:auto;bottom:0;margin-top:0;margin-bottom:-2px;border-radius:5px 5px 5px 0;-webkit-border-radius:5px 5px 5px 0;-moz-border-radius:5px 5px 5px 0;border-radius:5px 5px 5px 0}
.dropdown-submenu>a:after{display:block;content:" ";float:right;width:0;height:0;border-color:transparent;border-style:solid;border-width:5px 0 5px 5px;border-left-color:#ccc;margin-top:5px;margin-right:-10px}
.dropdown-submenu:hover>a:after{border-left-color:#fff}
.dropdown-submenu.pull-left{float:none}.dropdown-submenu.pull-left>.dropdown-menu{left:-100%;margin-left:10px;border-radius:6px 0 6px 6px;-webkit-border-radius:6px 0 6px 6px;-moz-border-radius:6px 0 6px 6px;border-radius:6px 0 6px 6px}
.dropdown .dropdown-menu .nav-header{padding-left:20px;padding-right:20px}
.typeahead{z-index:1051;margin-top:2px;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}
.well{min-height:20px;padding:19px;margin-bottom:20px;background-color:#f5f5f5;border:1px solid #e3e3e3;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px;-webkit-box-shadow:inset 0 1px 1px rgba(0,0,0,0.05);-moz-box-shadow:inset 0 1px 1px rgba(0,0,0,0.05);box-shadow:inset 0 1px 1px rgba(0,0,0,0.05)}.well blockquote{border-color:#ddd;border-color:rgba(0,0,0,0.15)}
.well-large{padding:24px;border-radius:6px;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px}
.well-small{padding:9px;border-radius:3px;-webkit-border-radius:3px;-moz-border-radius:3px;border-radius:3px}
.fade{opacity:0;-webkit-transition:opacity .15s linear;-moz-transition:opacity .15s linear;-o-transition:opacity .15s linear;transition:opacity .15s linear}.fade.in{opacity:1}
.collapse{position:relative;height:0;overflow:hidden;-webkit-transition:height .35s ease;-moz-transition:height .35s ease;-o-transition:height .35s ease;transition:height .35s ease}.collapse.in{height:auto}
.close{float:right;font-size:20px;font-weight:bold;line-height:20px;color:#000;text-shadow:0 1px 0 #fff;opacity:.2;filter:alpha(opacity=20)}.close:hover,.close:focus{color:#000;text-decoration:none;cursor:pointer;opacity:.4;filter:alpha(opacity=40)}
button.close{padding:0;cursor:pointer;background:transparent;border:0;-webkit-appearance:none}
.btn{display:inline-block;*display:inline;*zoom:1;padding:4px 12px;margin-bottom:0;font-size:13px;line-height:20px;text-align:center;vertical-align:middle;cursor:pointer;color:#333;text-shadow:0 1px 1px rgba(255,255,255,0.75);background-color:#f5f5f5;background-image:-moz-linear-gradient(top, #fff, #e6e6e6);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#fff), to(#e6e6e6));background-image:-webkit-linear-gradient(top, #fff, #e6e6e6);background-image:-o-linear-gradient(top, #fff, #e6e6e6);background-image:linear-gradient(to bottom, #fff, #e6e6e6);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffffffff', endColorstr='#ffe6e6e6', GradientType=0);border-color:#e6e6e6 #e6e6e6 #bfbfbf;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#e6e6e6;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false);border:1px solid #ccc;*border:0;border-bottom-color:#b3b3b3;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px;*margin-left:.3em;-webkit-box-shadow:inset 0 1px 0 rgba(255,255,255,.2), 0 1px 2px rgba(0,0,0,.05);-moz-box-shadow:inset 0 1px 0 rgba(255,255,255,.2), 0 1px 2px rgba(0,0,0,.05);box-shadow:inset 0 1px 0 rgba(255,255,255,.2), 0 1px 2px rgba(0,0,0,.05)}.btn:hover,.btn:focus,.btn:active,.btn.active,.btn.disabled,.btn[disabled]{color:#333;background-color:#e6e6e6;*background-color:#d9d9d9}
.btn:active,.btn.active{background-color:#ccc \9}
.btn:first-child{*margin-left:0}
.btn:hover,.btn:focus{color:#333;text-decoration:none;background-position:0 -15px;-webkit-transition:background-position .1s linear;-moz-transition:background-position .1s linear;-o-transition:background-position .1s linear;transition:background-position .1s linear}
.btn:focus{outline:thin dotted #333;outline:5px auto -webkit-focus-ring-color;outline-offset:-2px}
.btn.active,.btn:active{background-image:none;outline:0;-webkit-box-shadow:inset 0 2px 4px rgba(0,0,0,.15), 0 1px 2px rgba(0,0,0,.05);-moz-box-shadow:inset 0 2px 4px rgba(0,0,0,.15), 0 1px 2px rgba(0,0,0,.05);box-shadow:inset 0 2px 4px rgba(0,0,0,.15), 0 1px 2px rgba(0,0,0,.05)}
.btn.disabled,.btn[disabled]{cursor:default;background-image:none;opacity:.65;filter:alpha(opacity=65);-webkit-box-shadow:none;-moz-box-shadow:none;box-shadow:none}
.btn-large{padding:11px 19px;font-size:16.25px;border-radius:6px;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px}
.btn-large [class^="icon-"],.btn-large [class*=" icon-"]{margin-top:4px}
.btn-small{padding:2px 10px;font-size:11.049999999999999px;border-radius:3px;-webkit-border-radius:3px;-moz-border-radius:3px;border-radius:3px}
.btn-small [class^="icon-"],.btn-small [class*=" icon-"]{margin-top:0}
.btn-mini [class^="icon-"],.btn-mini [class*=" icon-"]{margin-top:-1px}
.btn-mini{padding:0 6px;font-size:9.75px;border-radius:3px;-webkit-border-radius:3px;-moz-border-radius:3px;border-radius:3px}
.btn-block{display:block;width:100%;padding-left:0;padding-right:0;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box}
.btn-block+.btn-block{margin-top:5px}
input[type="submit"].btn-block,input[type="reset"].btn-block,input[type="button"].btn-block{width:100%}
.btn-primary.active,.btn-warning.active,.btn-danger.active,.btn-success.active,.btn-info.active,.btn-inverse.active{color:rgba(255,255,255,0.75)}
.btn-primary{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#006dcc;background-image:-moz-linear-gradient(top, #08c, #04c);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#08c), to(#04c));background-image:-webkit-linear-gradient(top, #08c, #04c);background-image:-o-linear-gradient(top, #08c, #04c);background-image:linear-gradient(to bottom, #08c, #04c);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff0088cc', endColorstr='#ff0044cc', GradientType=0);border-color:#04c #04c #002a80;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#04c;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false)}.btn-primary:hover,.btn-primary:focus,.btn-primary:active,.btn-primary.active,.btn-primary.disabled,.btn-primary[disabled]{color:#fff;background-color:#04c;*background-color:#003bb3}
.btn-primary:active,.btn-primary.active{background-color:#039 \9}
.btn-warning{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#faa732;background-image:-moz-linear-gradient(top, #fbb450, #f89406);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#fbb450), to(#f89406));background-image:-webkit-linear-gradient(top, #fbb450, #f89406);background-image:-o-linear-gradient(top, #fbb450, #f89406);background-image:linear-gradient(to bottom, #fbb450, #f89406);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#fffbb450', endColorstr='#fff89406', GradientType=0);border-color:#f89406 #f89406 #ad6704;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#f89406;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false)}.btn-warning:hover,.btn-warning:focus,.btn-warning:active,.btn-warning.active,.btn-warning.disabled,.btn-warning[disabled]{color:#fff;background-color:#f89406;*background-color:#df8505}
.btn-warning:active,.btn-warning.active{background-color:#c67605 \9}
.btn-danger{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#da4f49;background-image:-moz-linear-gradient(top, #ee5f5b, #bd362f);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#ee5f5b), to(#bd362f));background-image:-webkit-linear-gradient(top, #ee5f5b, #bd362f);background-image:-o-linear-gradient(top, #ee5f5b, #bd362f);background-image:linear-gradient(to bottom, #ee5f5b, #bd362f);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffee5f5b', endColorstr='#ffbd362f', GradientType=0);border-color:#bd362f #bd362f #802420;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#bd362f;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false)}.btn-danger:hover,.btn-danger:focus,.btn-danger:active,.btn-danger.active,.btn-danger.disabled,.btn-danger[disabled]{color:#fff;background-color:#bd362f;*background-color:#a9302a}
.btn-danger:active,.btn-danger.active{background-color:#942a25 \9}
.btn-success{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#5bb75b;background-image:-moz-linear-gradient(top, #62c462, #51a351);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#62c462), to(#51a351));background-image:-webkit-linear-gradient(top, #62c462, #51a351);background-image:-o-linear-gradient(top, #62c462, #51a351);background-image:linear-gradient(to bottom, #62c462, #51a351);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff62c462', endColorstr='#ff51a351', GradientType=0);border-color:#51a351 #51a351 #387038;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#51a351;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false)}.btn-success:hover,.btn-success:focus,.btn-success:active,.btn-success.active,.btn-success.disabled,.btn-success[disabled]{color:#fff;background-color:#51a351;*background-color:#499249}
.btn-success:active,.btn-success.active{background-color:#408140 \9}
.btn-info{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#49afcd;background-image:-moz-linear-gradient(top, #5bc0de, #2f96b4);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#5bc0de), to(#2f96b4));background-image:-webkit-linear-gradient(top, #5bc0de, #2f96b4);background-image:-o-linear-gradient(top, #5bc0de, #2f96b4);background-image:linear-gradient(to bottom, #5bc0de, #2f96b4);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff5bc0de', endColorstr='#ff2f96b4', GradientType=0);border-color:#2f96b4 #2f96b4 #1f6377;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#2f96b4;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false)}.btn-info:hover,.btn-info:focus,.btn-info:active,.btn-info.active,.btn-info.disabled,.btn-info[disabled]{color:#fff;background-color:#2f96b4;*background-color:#2a85a0}
.btn-info:active,.btn-info.active{background-color:#24748c \9}
.btn-inverse{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#363636;background-image:-moz-linear-gradient(top, #444, #222);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#444), to(#222));background-image:-webkit-linear-gradient(top, #444, #222);background-image:-o-linear-gradient(top, #444, #222);background-image:linear-gradient(to bottom, #444, #222);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff444444', endColorstr='#ff222222', GradientType=0);border-color:#222 #222 #000;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#222;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false)}.btn-inverse:hover,.btn-inverse:focus,.btn-inverse:active,.btn-inverse.active,.btn-inverse.disabled,.btn-inverse[disabled]{color:#fff;background-color:#222;*background-color:#151515}
.btn-inverse:active,.btn-inverse.active{background-color:#080808 \9}
button.btn,input[type="submit"].btn{*padding-top:3px;*padding-bottom:3px}button.btn::-moz-focus-inner,input[type="submit"].btn::-moz-focus-inner{padding:0;border:0}
button.btn.btn-large,input[type="submit"].btn.btn-large{*padding-top:7px;*padding-bottom:7px}
button.btn.btn-small,input[type="submit"].btn.btn-small{*padding-top:3px;*padding-bottom:3px}
button.btn.btn-mini,input[type="submit"].btn.btn-mini{*padding-top:1px;*padding-bottom:1px}
.btn-link,.btn-link:active,.btn-link[disabled]{background-color:transparent;background-image:none;-webkit-box-shadow:none;-moz-box-shadow:none;box-shadow:none}
.btn-link{border-color:transparent;cursor:pointer;color:#08c;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.btn-link:hover,.btn-link:focus{color:#005580;text-decoration:underline;background-color:transparent}
.btn-link[disabled]:hover,.btn-link[disabled]:focus{color:#333;text-decoration:none}
.btn-group{position:relative;display:inline-block;*display:inline;*zoom:1;font-size:0;vertical-align:middle;white-space:nowrap;*margin-left:.3em}.btn-group:first-child{*margin-left:0}
.btn-group+.btn-group{margin-left:5px}
.btn-toolbar{font-size:0;margin-top:10px;margin-bottom:10px}.btn-toolbar>.btn+.btn,.btn-toolbar>.btn-group+.btn,.btn-toolbar>.btn+.btn-group{margin-left:5px}
.btn-group>.btn{position:relative;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.btn-group>.btn+.btn{margin-left:-1px}
.btn-group>.btn,.btn-group>.dropdown-menu,.btn-group>.popover{font-size:13px}
.btn-group>.btn-mini{font-size:9.75px}
.btn-group>.btn-small{font-size:11.049999999999999px}
.btn-group>.btn-large{font-size:16.25px}
.btn-group>.btn:first-child{margin-left:0;-webkit-border-top-left-radius:4px;-moz-border-radius-topleft:4px;border-top-left-radius:4px;-webkit-border-bottom-left-radius:4px;-moz-border-radius-bottomleft:4px;border-bottom-left-radius:4px}
.btn-group>.btn:last-child,.btn-group>.dropdown-toggle{-webkit-border-top-right-radius:4px;-moz-border-radius-topright:4px;border-top-right-radius:4px;-webkit-border-bottom-right-radius:4px;-moz-border-radius-bottomright:4px;border-bottom-right-radius:4px}
.btn-group>.btn.large:first-child{margin-left:0;-webkit-border-top-left-radius:6px;-moz-border-radius-topleft:6px;border-top-left-radius:6px;-webkit-border-bottom-left-radius:6px;-moz-border-radius-bottomleft:6px;border-bottom-left-radius:6px}
.btn-group>.btn.large:last-child,.btn-group>.large.dropdown-toggle{-webkit-border-top-right-radius:6px;-moz-border-radius-topright:6px;border-top-right-radius:6px;-webkit-border-bottom-right-radius:6px;-moz-border-radius-bottomright:6px;border-bottom-right-radius:6px}
.btn-group>.btn:hover,.btn-group>.btn:focus,.btn-group>.btn:active,.btn-group>.btn.active{z-index:2}
.btn-group .dropdown-toggle:active,.btn-group.open .dropdown-toggle{outline:0}
.btn-group>.btn+.dropdown-toggle{padding-left:8px;padding-right:8px;-webkit-box-shadow:inset 1px 0 0 rgba(255,255,255,.125), inset 0 1px 0 rgba(255,255,255,.2), 0 1px 2px rgba(0,0,0,.05);-moz-box-shadow:inset 1px 0 0 rgba(255,255,255,.125), inset 0 1px 0 rgba(255,255,255,.2), 0 1px 2px rgba(0,0,0,.05);box-shadow:inset 1px 0 0 rgba(255,255,255,.125), inset 0 1px 0 rgba(255,255,255,.2), 0 1px 2px rgba(0,0,0,.05);*padding-top:5px;*padding-bottom:5px}
.btn-group>.btn-mini+.dropdown-toggle{padding-left:5px;padding-right:5px;*padding-top:2px;*padding-bottom:2px}
.btn-group>.btn-small+.dropdown-toggle{*padding-top:5px;*padding-bottom:4px}
.btn-group>.btn-large+.dropdown-toggle{padding-left:12px;padding-right:12px;*padding-top:7px;*padding-bottom:7px}
.btn-group.open .dropdown-toggle{background-image:none;-webkit-box-shadow:inset 0 2px 4px rgba(0,0,0,.15), 0 1px 2px rgba(0,0,0,.05);-moz-box-shadow:inset 0 2px 4px rgba(0,0,0,.15), 0 1px 2px rgba(0,0,0,.05);box-shadow:inset 0 2px 4px rgba(0,0,0,.15), 0 1px 2px rgba(0,0,0,.05)}
.btn-group.open .btn.dropdown-toggle{background-color:#e6e6e6}
.btn-group.open .btn-primary.dropdown-toggle{background-color:#04c}
.btn-group.open .btn-warning.dropdown-toggle{background-color:#f89406}
.btn-group.open .btn-danger.dropdown-toggle{background-color:#bd362f}
.btn-group.open .btn-success.dropdown-toggle{background-color:#51a351}
.btn-group.open .btn-info.dropdown-toggle{background-color:#2f96b4}
.btn-group.open .btn-inverse.dropdown-toggle{background-color:#222}
.btn .caret{margin-top:8px;margin-left:0}
.btn-large .caret{margin-top:6px}
.btn-large .caret{border-left-width:5px;border-right-width:5px;border-top-width:5px}
.btn-mini .caret,.btn-small .caret{margin-top:8px}
.dropup .btn-large .caret{border-bottom-width:5px}
.btn-primary .caret,.btn-warning .caret,.btn-danger .caret,.btn-info .caret,.btn-success .caret,.btn-inverse .caret{border-top-color:#fff;border-bottom-color:#fff}
.btn-group-vertical{display:inline-block;*display:inline;*zoom:1}
.btn-group-vertical>.btn{display:block;float:none;max-width:100%;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.btn-group-vertical>.btn+.btn{margin-left:0;margin-top:-1px}
.btn-group-vertical>.btn:first-child{border-radius:4px 4px 0 0;-webkit-border-radius:4px 4px 0 0;-moz-border-radius:4px 4px 0 0;border-radius:4px 4px 0 0}
.btn-group-vertical>.btn:last-child{border-radius:0 0 4px 4px;-webkit-border-radius:0 0 4px 4px;-moz-border-radius:0 0 4px 4px;border-radius:0 0 4px 4px}
.btn-group-vertical>.btn-large:first-child{border-radius:6px 6px 0 0;-webkit-border-radius:6px 6px 0 0;-moz-border-radius:6px 6px 0 0;border-radius:6px 6px 0 0}
.btn-group-vertical>.btn-large:last-child{border-radius:0 0 6px 6px;-webkit-border-radius:0 0 6px 6px;-moz-border-radius:0 0 6px 6px;border-radius:0 0 6px 6px}
.alert{padding:8px 35px 8px 14px;margin-bottom:20px;text-shadow:0 1px 0 rgba(255,255,255,0.5);background-color:#fcf8e3;border:1px solid #fbeed5;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}
.alert,.alert h4{color:#c09853}
.alert h4{margin:0}
.alert .close{position:relative;top:-2px;right:-21px;line-height:20px}
.alert-success{background-color:#dff0d8;border-color:#d6e9c6;color:#468847}
.alert-success h4{color:#468847}
.alert-danger,.alert-error{background-color:#f2dede;border-color:#eed3d7;color:#b94a48}
.alert-danger h4,.alert-error h4{color:#b94a48}
.alert-info{background-color:#d9edf7;border-color:#bce8f1;color:#3a87ad}
.alert-info h4{color:#3a87ad}
.alert-block{padding-top:14px;padding-bottom:14px}
.alert-block>p,.alert-block>ul{margin-bottom:0}
.alert-block p+p{margin-top:5px}
.nav{margin-left:0;margin-bottom:20px;list-style:none}
.nav>li>a{display:block}
.nav>li>a:hover,.nav>li>a:focus{text-decoration:none;background-color:#eee}
.nav>li>a>img{max-width:none}
.nav>.pull-right{float:right}
.nav-header{display:block;padding:3px 15px;font-size:11px;font-weight:bold;line-height:20px;color:#999;text-shadow:0 1px 0 rgba(255,255,255,0.5);text-transform:uppercase}
.nav li+.nav-header{margin-top:9px}
.nav-list{padding-left:15px;padding-right:15px;margin-bottom:0}
.nav-list>li>a,.nav-list .nav-header{margin-left:-15px;margin-right:-15px;text-shadow:0 1px 0 rgba(255,255,255,0.5)}
.nav-list>li>a{padding:3px 15px}
.nav-list>.active>a,.nav-list>.active>a:hover,.nav-list>.active>a:focus{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.2);background-color:#08c}
.nav-list [class^="icon-"],.nav-list [class*=" icon-"]{margin-right:2px}
.nav-list .divider{*width:100%;height:1px;margin:9px 1px;*margin:-5px 0 5px;overflow:hidden;background-color:#e5e5e5;border-bottom:1px solid #fff}
.nav-tabs,.nav-pills{*zoom:1}.nav-tabs:before,.nav-pills:before,.nav-tabs:after,.nav-pills:after{display:table;content:"";line-height:0}
.nav-tabs:after,.nav-pills:after{clear:both}
.nav-tabs>li,.nav-pills>li{float:left}
.nav-tabs>li>a,.nav-pills>li>a{padding-right:12px;padding-left:12px;margin-right:2px;line-height:14px}
.nav-tabs{border-bottom:1px solid #ddd}
.nav-tabs>li{margin-bottom:-1px}
.nav-tabs>li>a{padding-top:8px;padding-bottom:8px;line-height:20px;border:1px solid transparent;border-radius:4px 4px 0 0;-webkit-border-radius:4px 4px 0 0;-moz-border-radius:4px 4px 0 0;border-radius:4px 4px 0 0}.nav-tabs>li>a:hover,.nav-tabs>li>a:focus{border-color:#eee #eee #ddd}
.nav-tabs>.active>a,.nav-tabs>.active>a:hover,.nav-tabs>.active>a:focus{color:#555;background-color:#fff;border:1px solid #ddd;border-bottom-color:transparent;cursor:default}
.nav-pills>li>a{padding-top:8px;padding-bottom:8px;margin-top:2px;margin-bottom:2px;border-radius:5px;-webkit-border-radius:5px;-moz-border-radius:5px;border-radius:5px}
.nav-pills>.active>a,.nav-pills>.active>a:hover,.nav-pills>.active>a:focus{color:#fff;background-color:#08c}
.nav-stacked>li{float:none}
.nav-stacked>li>a{margin-right:0}
.nav-tabs.nav-stacked{border-bottom:0}
.nav-tabs.nav-stacked>li>a{border:1px solid #ddd;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.nav-tabs.nav-stacked>li:first-child>a{-webkit-border-top-right-radius:4px;-moz-border-radius-topright:4px;border-top-right-radius:4px;-webkit-border-top-left-radius:4px;-moz-border-radius-topleft:4px;border-top-left-radius:4px}
.nav-tabs.nav-stacked>li:last-child>a{-webkit-border-bottom-right-radius:4px;-moz-border-radius-bottomright:4px;border-bottom-right-radius:4px;-webkit-border-bottom-left-radius:4px;-moz-border-radius-bottomleft:4px;border-bottom-left-radius:4px}
.nav-tabs.nav-stacked>li>a:hover,.nav-tabs.nav-stacked>li>a:focus{border-color:#ddd;z-index:2}
.nav-pills.nav-stacked>li>a{margin-bottom:3px}
.nav-pills.nav-stacked>li:last-child>a{margin-bottom:1px}
.nav-tabs .dropdown-menu{border-radius:0 0 6px 6px;-webkit-border-radius:0 0 6px 6px;-moz-border-radius:0 0 6px 6px;border-radius:0 0 6px 6px}
.nav-pills .dropdown-menu{border-radius:6px;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px}
.nav .dropdown-toggle .caret{border-top-color:#08c;border-bottom-color:#08c;margin-top:6px}
.nav .dropdown-toggle:hover .caret,.nav .dropdown-toggle:focus .caret{border-top-color:#005580;border-bottom-color:#005580}
.nav-tabs .dropdown-toggle .caret{margin-top:8px}
.nav .active .dropdown-toggle .caret{border-top-color:#fff;border-bottom-color:#fff}
.nav-tabs .active .dropdown-toggle .caret{border-top-color:#555;border-bottom-color:#555}
.nav>.dropdown.active>a:hover,.nav>.dropdown.active>a:focus{cursor:pointer}
.nav-tabs .open .dropdown-toggle,.nav-pills .open .dropdown-toggle,.nav>li.dropdown.open.active>a:hover,.nav>li.dropdown.open.active>a:focus{color:#fff;background-color:#999;border-color:#999}
.nav li.dropdown.open .caret,.nav li.dropdown.open.active .caret,.nav li.dropdown.open a:hover .caret,.nav li.dropdown.open a:focus .caret{border-top-color:#fff;border-bottom-color:#fff;opacity:1;filter:alpha(opacity=100)}
.tabs-stacked .open>a:hover,.tabs-stacked .open>a:focus{border-color:#999}
.tabbable{*zoom:1}.tabbable:before,.tabbable:after{display:table;content:"";line-height:0}
.tabbable:after{clear:both}
.tab-content{overflow:auto}
.tabs-below>.nav-tabs,.tabs-right>.nav-tabs,.tabs-left>.nav-tabs{border-bottom:0}
.tab-content>.tab-pane,.pill-content>.pill-pane{display:none}
.tab-content>.active,.pill-content>.active{display:block}
.tabs-below>.nav-tabs{border-top:1px solid #ddd}
.tabs-below>.nav-tabs>li{margin-top:-1px;margin-bottom:0}
.tabs-below>.nav-tabs>li>a{border-radius:0 0 4px 4px;-webkit-border-radius:0 0 4px 4px;-moz-border-radius:0 0 4px 4px;border-radius:0 0 4px 4px}.tabs-below>.nav-tabs>li>a:hover,.tabs-below>.nav-tabs>li>a:focus{border-bottom-color:transparent;border-top-color:#ddd}
.tabs-below>.nav-tabs>.active>a,.tabs-below>.nav-tabs>.active>a:hover,.tabs-below>.nav-tabs>.active>a:focus{border-color:transparent #ddd #ddd #ddd}
.tabs-left>.nav-tabs>li,.tabs-right>.nav-tabs>li{float:none}
.tabs-left>.nav-tabs>li>a,.tabs-right>.nav-tabs>li>a{min-width:74px;margin-right:0;margin-bottom:3px}
.tabs-left>.nav-tabs{float:left;margin-right:19px;border-right:1px solid #ddd}
.tabs-left>.nav-tabs>li>a{margin-right:-1px;border-radius:4px 0 0 4px;-webkit-border-radius:4px 0 0 4px;-moz-border-radius:4px 0 0 4px;border-radius:4px 0 0 4px}
.tabs-left>.nav-tabs>li>a:hover,.tabs-left>.nav-tabs>li>a:focus{border-color:#eee #ddd #eee #eee}
.tabs-left>.nav-tabs .active>a,.tabs-left>.nav-tabs .active>a:hover,.tabs-left>.nav-tabs .active>a:focus{border-color:#ddd transparent #ddd #ddd;*border-right-color:#fff}
.tabs-right>.nav-tabs{float:right;margin-left:19px;border-left:1px solid #ddd}
.tabs-right>.nav-tabs>li>a{margin-left:-1px;border-radius:0 4px 4px 0;-webkit-border-radius:0 4px 4px 0;-moz-border-radius:0 4px 4px 0;border-radius:0 4px 4px 0}
.tabs-right>.nav-tabs>li>a:hover,.tabs-right>.nav-tabs>li>a:focus{border-color:#eee #eee #eee #ddd}
.tabs-right>.nav-tabs .active>a,.tabs-right>.nav-tabs .active>a:hover,.tabs-right>.nav-tabs .active>a:focus{border-color:#ddd #ddd #ddd transparent;*border-left-color:#fff}
.nav>.disabled>a{color:#999}
.nav>.disabled>a:hover,.nav>.disabled>a:focus{text-decoration:none;background-color:transparent;cursor:default}
.navbar{overflow:visible;margin-bottom:20px;*position:relative;*z-index:2}
.navbar-inner{min-height:36px;padding-left:20px;padding-right:20px;background-color:#fafafa;background-image:-moz-linear-gradient(top, #fff, #f2f2f2);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#fff), to(#f2f2f2));background-image:-webkit-linear-gradient(top, #fff, #f2f2f2);background-image:-o-linear-gradient(top, #fff, #f2f2f2);background-image:linear-gradient(to bottom, #fff, #f2f2f2);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffffffff', endColorstr='#fff2f2f2', GradientType=0);border:1px solid #d4d4d4;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px;-webkit-box-shadow:0 1px 4px rgba(0,0,0,0.065);-moz-box-shadow:0 1px 4px rgba(0,0,0,0.065);box-shadow:0 1px 4px rgba(0,0,0,0.065);*zoom:1}.navbar-inner:before,.navbar-inner:after{display:table;content:"";line-height:0}
.navbar-inner:after{clear:both}
.navbar .container{width:auto}
.nav-collapse.collapse{height:auto;overflow:visible}
.navbar .brand{float:left;display:block;padding:8px 20px 8px;margin-left:-20px;font-size:20px;font-weight:200;color:#777;text-shadow:0 1px 0 #fff}.navbar .brand:hover,.navbar .brand:focus{text-decoration:none}
.navbar-text{margin-bottom:0;line-height:36px;color:#777}
.navbar-link{color:#777}.navbar-link:hover,.navbar-link:focus{color:#333}
.navbar .divider-vertical{height:36px;margin:0 9px;border-left:1px solid #f2f2f2;border-right:1px solid #fff}
.navbar .btn,.navbar .btn-group{margin-top:3px}
.navbar .btn-group .btn,.navbar .input-prepend .btn,.navbar .input-append .btn,.navbar .input-prepend .btn-group,.navbar .input-append .btn-group{margin-top:0}
.navbar-form{margin-bottom:0;*zoom:1}.navbar-form:before,.navbar-form:after{display:table;content:"";line-height:0}
.navbar-form:after{clear:both}
.navbar-form input,.navbar-form select,.navbar-form .radio,.navbar-form .checkbox{margin-top:3px}
.navbar-form input,.navbar-form select,.navbar-form .btn{display:inline-block;margin-bottom:0}
.navbar-form input[type="image"],.navbar-form input[type="checkbox"],.navbar-form input[type="radio"]{margin-top:3px}
.navbar-form .input-append,.navbar-form .input-prepend{margin-top:5px;white-space:nowrap}.navbar-form .input-append input,.navbar-form .input-prepend input{margin-top:0}
.navbar-search{position:relative;float:left;margin-top:3px;margin-bottom:0}.navbar-search .search-query{margin-bottom:0;padding:4px 14px;font-family:"Helvetica Neue",Helvetica,Arial,sans-serif;font-size:13px;font-weight:normal;line-height:1;border-radius:15px;-webkit-border-radius:15px;-moz-border-radius:15px;border-radius:15px}
.navbar-static-top{position:static;margin-bottom:0}.navbar-static-top .navbar-inner{border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.navbar-fixed-top,.navbar-fixed-bottom{position:fixed;right:0;left:0;z-index:1030;margin-bottom:0}
.navbar-fixed-top .navbar-inner,.navbar-static-top .navbar-inner{border-width:0 0 1px}
.navbar-fixed-bottom .navbar-inner{border-width:1px 0 0}
.navbar-fixed-top .navbar-inner,.navbar-fixed-bottom .navbar-inner{padding-left:0;padding-right:0;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
.navbar-static-top .container,.navbar-fixed-top .container,.navbar-fixed-bottom .container{width:940px}
.navbar-fixed-top{top:0}
.navbar-fixed-top .navbar-inner,.navbar-static-top .navbar-inner{-webkit-box-shadow:0 1px 10px rgba(0,0,0,.1);-moz-box-shadow:0 1px 10px rgba(0,0,0,.1);box-shadow:0 1px 10px rgba(0,0,0,.1)}
.navbar-fixed-bottom{bottom:0}.navbar-fixed-bottom .navbar-inner{-webkit-box-shadow:0 -1px 10px rgba(0,0,0,.1);-moz-box-shadow:0 -1px 10px rgba(0,0,0,.1);box-shadow:0 -1px 10px rgba(0,0,0,.1)}
.navbar .nav{position:relative;left:0;display:block;float:left;margin:0 10px 0 0}
.navbar .nav.pull-right{float:right;margin-right:0}
.navbar .nav>li{float:left}
.navbar .nav>li>a{float:none;padding:8px 15px 8px;color:#777;text-decoration:none;text-shadow:0 1px 0 #fff}
.navbar .nav .dropdown-toggle .caret{margin-top:8px}
.navbar .nav>li>a:focus,.navbar .nav>li>a:hover{background-color:transparent;color:#333;text-decoration:none}
.navbar .nav>.active>a,.navbar .nav>.active>a:hover,.navbar .nav>.active>a:focus{color:#555;text-decoration:none;background-color:#e5e5e5;-webkit-box-shadow:inset 0 3px 8px rgba(0,0,0,0.125);-moz-box-shadow:inset 0 3px 8px rgba(0,0,0,0.125);box-shadow:inset 0 3px 8px rgba(0,0,0,0.125)}
.navbar .btn-navbar{display:none;float:right;padding:7px 10px;margin-left:5px;margin-right:5px;color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#ededed;background-image:-moz-linear-gradient(top, #f2f2f2, #e5e5e5);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#f2f2f2), to(#e5e5e5));background-image:-webkit-linear-gradient(top, #f2f2f2, #e5e5e5);background-image:-o-linear-gradient(top, #f2f2f2, #e5e5e5);background-image:linear-gradient(to bottom, #f2f2f2, #e5e5e5);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#fff2f2f2', endColorstr='#ffe5e5e5', GradientType=0);border-color:#e5e5e5 #e5e5e5 #bfbfbf;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#e5e5e5;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false);-webkit-box-shadow:inset 0 1px 0 rgba(255,255,255,.1), 0 1px 0 rgba(255,255,255,.075);-moz-box-shadow:inset 0 1px 0 rgba(255,255,255,.1), 0 1px 0 rgba(255,255,255,.075);box-shadow:inset 0 1px 0 rgba(255,255,255,.1), 0 1px 0 rgba(255,255,255,.075)}.navbar .btn-navbar:hover,.navbar .btn-navbar:focus,.navbar .btn-navbar:active,.navbar .btn-navbar.active,.navbar .btn-navbar.disabled,.navbar .btn-navbar[disabled]{color:#fff;background-color:#e5e5e5;*background-color:#d9d9d9}
.navbar .btn-navbar:active,.navbar .btn-navbar.active{background-color:#ccc \9}
.navbar .btn-navbar .icon-bar{display:block;width:18px;height:2px;background-color:#f5f5f5;-webkit-border-radius:1px;-moz-border-radius:1px;border-radius:1px;-webkit-box-shadow:0 1px 0 rgba(0,0,0,0.25);-moz-box-shadow:0 1px 0 rgba(0,0,0,0.25);box-shadow:0 1px 0 rgba(0,0,0,0.25)}
.btn-navbar .icon-bar+.icon-bar{margin-top:3px}
.navbar .nav>li>.dropdown-menu:before{content:'';display:inline-block;border-left:7px solid transparent;border-right:7px solid transparent;border-bottom:7px solid #ccc;border-bottom-color:rgba(0,0,0,0.2);position:absolute;top:-7px;left:9px}
.navbar .nav>li>.dropdown-menu:after{content:'';display:inline-block;border-left:6px solid transparent;border-right:6px solid transparent;border-bottom:6px solid #fff;position:absolute;top:-6px;left:10px}
.navbar-fixed-bottom .nav>li>.dropdown-menu:before{border-top:7px solid #ccc;border-top-color:rgba(0,0,0,0.2);border-bottom:0;bottom:-7px;top:auto}
.navbar-fixed-bottom .nav>li>.dropdown-menu:after{border-top:6px solid #fff;border-bottom:0;bottom:-6px;top:auto}
.navbar .nav li.dropdown>a:hover .caret,.navbar .nav li.dropdown>a:focus .caret{border-top-color:#333;border-bottom-color:#333}
.navbar .nav li.dropdown.open>.dropdown-toggle,.navbar .nav li.dropdown.active>.dropdown-toggle,.navbar .nav li.dropdown.open.active>.dropdown-toggle{background-color:#e5e5e5;color:#555}
.navbar .nav li.dropdown>.dropdown-toggle .caret{border-top-color:#777;border-bottom-color:#777}
.navbar .nav li.dropdown.open>.dropdown-toggle .caret,.navbar .nav li.dropdown.active>.dropdown-toggle .caret,.navbar .nav li.dropdown.open.active>.dropdown-toggle .caret{border-top-color:#555;border-bottom-color:#555}
.navbar .pull-right>li>.dropdown-menu,.navbar .nav>li>.dropdown-menu.pull-right{left:auto;right:0}.navbar .pull-right>li>.dropdown-menu:before,.navbar .nav>li>.dropdown-menu.pull-right:before{left:auto;right:12px}
.navbar .pull-right>li>.dropdown-menu:after,.navbar .nav>li>.dropdown-menu.pull-right:after{left:auto;right:13px}
.navbar .pull-right>li>.dropdown-menu .dropdown-menu,.navbar .nav>li>.dropdown-menu.pull-right .dropdown-menu{left:auto;right:100%;margin-left:0;margin-right:-1px;border-radius:6px 0 6px 6px;-webkit-border-radius:6px 0 6px 6px;-moz-border-radius:6px 0 6px 6px;border-radius:6px 0 6px 6px}
.navbar-inverse .navbar-inner{background-color:#1b1b1b;background-image:-moz-linear-gradient(top, #222, #111);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#222), to(#111));background-image:-webkit-linear-gradient(top, #222, #111);background-image:-o-linear-gradient(top, #222, #111);background-image:linear-gradient(to bottom, #222, #111);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff222222', endColorstr='#ff111111', GradientType=0);border-color:#252525}
.navbar-inverse .brand,.navbar-inverse .nav>li>a{color:#999;text-shadow:0 -1px 0 rgba(0,0,0,0.25)}.navbar-inverse .brand:hover,.navbar-inverse .nav>li>a:hover,.navbar-inverse .brand:focus,.navbar-inverse .nav>li>a:focus{color:#fff}
.navbar-inverse .brand{color:#999}
.navbar-inverse .navbar-text{color:#999}
.navbar-inverse .nav>li>a:focus,.navbar-inverse .nav>li>a:hover{background-color:transparent;color:#fff}
.navbar-inverse .nav .active>a,.navbar-inverse .nav .active>a:hover,.navbar-inverse .nav .active>a:focus{color:#fff;background-color:#111}
.navbar-inverse .navbar-link{color:#999}.navbar-inverse .navbar-link:hover,.navbar-inverse .navbar-link:focus{color:#fff}
.navbar-inverse .divider-vertical{border-left-color:#111;border-right-color:#222}
.navbar-inverse .nav li.dropdown.open>.dropdown-toggle,.navbar-inverse .nav li.dropdown.active>.dropdown-toggle,.navbar-inverse .nav li.dropdown.open.active>.dropdown-toggle{background-color:#111;color:#fff}
.navbar-inverse .nav li.dropdown>a:hover .caret,.navbar-inverse .nav li.dropdown>a:focus .caret{border-top-color:#fff;border-bottom-color:#fff}
.navbar-inverse .nav li.dropdown>.dropdown-toggle .caret{border-top-color:#999;border-bottom-color:#999}
.navbar-inverse .nav li.dropdown.open>.dropdown-toggle .caret,.navbar-inverse .nav li.dropdown.active>.dropdown-toggle .caret,.navbar-inverse .nav li.dropdown.open.active>.dropdown-toggle .caret{border-top-color:#fff;border-bottom-color:#fff}
.navbar-inverse .navbar-search .search-query{color:#fff;background-color:#515151;border-color:#111;-webkit-box-shadow:inset 0 1px 2px rgba(0,0,0,.1), 0 1px 0 rgba(255,255,255,.15);-moz-box-shadow:inset 0 1px 2px rgba(0,0,0,.1), 0 1px 0 rgba(255,255,255,.15);box-shadow:inset 0 1px 2px rgba(0,0,0,.1), 0 1px 0 rgba(255,255,255,.15);-webkit-transition:none;-moz-transition:none;-o-transition:none;transition:none}.navbar-inverse .navbar-search .search-query:-moz-placeholder{color:#ccc}
.navbar-inverse .navbar-search .search-query:-ms-input-placeholder{color:#ccc}
.navbar-inverse .navbar-search .search-query::-webkit-input-placeholder{color:#ccc}
.navbar-inverse .navbar-search .search-query:focus,.navbar-inverse .navbar-search .search-query.focused{padding:5px 15px;color:#333;text-shadow:0 1px 0 #fff;background-color:#fff;border:0;-webkit-box-shadow:0 0 3px rgba(0,0,0,0.15);-moz-box-shadow:0 0 3px rgba(0,0,0,0.15);box-shadow:0 0 3px rgba(0,0,0,0.15);outline:0}
.navbar-inverse .btn-navbar{color:#fff;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#0e0e0e;background-image:-moz-linear-gradient(top, #151515, #040404);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#151515), to(#040404));background-image:-webkit-linear-gradient(top, #151515, #040404);background-image:-o-linear-gradient(top, #151515, #040404);background-image:linear-gradient(to bottom, #151515, #040404);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff151515', endColorstr='#ff040404', GradientType=0);border-color:#040404 #040404 #000;border-color:rgba(0,0,0,0.1) rgba(0,0,0,0.1) rgba(0,0,0,0.25);*background-color:#040404;filter:progid:DXImageTransform.Microsoft.gradient(enabled = false)}.navbar-inverse .btn-navbar:hover,.navbar-inverse .btn-navbar:focus,.navbar-inverse .btn-navbar:active,.navbar-inverse .btn-navbar.active,.navbar-inverse .btn-navbar.disabled,.navbar-inverse .btn-navbar[disabled]{color:#fff;background-color:#040404;*background-color:#000}
.navbar-inverse .btn-navbar:active,.navbar-inverse .btn-navbar.active{background-color:#000 \9}
.breadcrumb{padding:8px 15px;margin:0 0 20px;list-style:none;background-color:#f5f5f5;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}.breadcrumb>li{display:inline-block;*display:inline;*zoom:1;text-shadow:0 1px 0 #fff}.breadcrumb>li>.divider{padding:0 5px;color:#ccc}
.breadcrumb>.active{color:#999}
.pagination{margin:20px 0}
.pagination ul{display:inline-block;*display:inline;*zoom:1;margin-left:0;margin-bottom:0;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px;-webkit-box-shadow:0 1px 2px rgba(0,0,0,0.05);-moz-box-shadow:0 1px 2px rgba(0,0,0,0.05);box-shadow:0 1px 2px rgba(0,0,0,0.05)}
.pagination ul>li{display:inline}
.pagination ul>li>a,.pagination ul>li>span{float:left;padding:4px 12px;line-height:20px;text-decoration:none;background-color:#fff;border:1px solid #ddd;border-left-width:0}
.pagination ul>li>a:hover,.pagination ul>li>a:focus,.pagination ul>.active>a,.pagination ul>.active>span{background-color:#f5f5f5}
.pagination ul>.active>a,.pagination ul>.active>span{color:#999;cursor:default}
.pagination ul>.disabled>span,.pagination ul>.disabled>a,.pagination ul>.disabled>a:hover,.pagination ul>.disabled>a:focus{color:#999;background-color:transparent;cursor:default}
.pagination ul>li:first-child>a,.pagination ul>li:first-child>span{border-left-width:1px;-webkit-border-top-left-radius:4px;-moz-border-radius-topleft:4px;border-top-left-radius:4px;-webkit-border-bottom-left-radius:4px;-moz-border-radius-bottomleft:4px;border-bottom-left-radius:4px}
.pagination ul>li:last-child>a,.pagination ul>li:last-child>span{-webkit-border-top-right-radius:4px;-moz-border-radius-topright:4px;border-top-right-radius:4px;-webkit-border-bottom-right-radius:4px;-moz-border-radius-bottomright:4px;border-bottom-right-radius:4px}
.pagination-centered{text-align:center}
.pagination-right{text-align:right}
.pagination-large ul>li>a,.pagination-large ul>li>span{padding:11px 19px;font-size:16.25px}
.pagination-large ul>li:first-child>a,.pagination-large ul>li:first-child>span{-webkit-border-top-left-radius:6px;-moz-border-radius-topleft:6px;border-top-left-radius:6px;-webkit-border-bottom-left-radius:6px;-moz-border-radius-bottomleft:6px;border-bottom-left-radius:6px}
.pagination-large ul>li:last-child>a,.pagination-large ul>li:last-child>span{-webkit-border-top-right-radius:6px;-moz-border-radius-topright:6px;border-top-right-radius:6px;-webkit-border-bottom-right-radius:6px;-moz-border-radius-bottomright:6px;border-bottom-right-radius:6px}
.pagination-mini ul>li:first-child>a,.pagination-small ul>li:first-child>a,.pagination-mini ul>li:first-child>span,.pagination-small ul>li:first-child>span{-webkit-border-top-left-radius:3px;-moz-border-radius-topleft:3px;border-top-left-radius:3px;-webkit-border-bottom-left-radius:3px;-moz-border-radius-bottomleft:3px;border-bottom-left-radius:3px}
.pagination-mini ul>li:last-child>a,.pagination-small ul>li:last-child>a,.pagination-mini ul>li:last-child>span,.pagination-small ul>li:last-child>span{-webkit-border-top-right-radius:3px;-moz-border-radius-topright:3px;border-top-right-radius:3px;-webkit-border-bottom-right-radius:3px;-moz-border-radius-bottomright:3px;border-bottom-right-radius:3px}
.pagination-small ul>li>a,.pagination-small ul>li>span{padding:2px 10px;font-size:11.049999999999999px}
.pagination-mini ul>li>a,.pagination-mini ul>li>span{padding:0 6px;font-size:9.75px}
.pager{margin:20px 0;list-style:none;text-align:center;*zoom:1}.pager:before,.pager:after{display:table;content:"";line-height:0}
.pager:after{clear:both}
.pager li{display:inline}
.pager li>a,.pager li>span{display:inline-block;padding:5px 14px;background-color:#fff;border:1px solid #ddd;border-radius:15px;-webkit-border-radius:15px;-moz-border-radius:15px;border-radius:15px}
.pager li>a:hover,.pager li>a:focus{text-decoration:none;background-color:#f5f5f5}
.pager .next>a,.pager .next>span{float:right}
.pager .previous>a,.pager .previous>span{float:left}
.pager .disabled>a,.pager .disabled>a:hover,.pager .disabled>a:focus,.pager .disabled>span{color:#999;background-color:#fff;cursor:default}
.modal-backdrop{position:fixed;top:0;right:0;bottom:0;left:0;z-index:1040;background-color:#000}.modal-backdrop.fade{opacity:0}
.modal-backdrop,.modal-backdrop.fade.in{opacity:.8;filter:alpha(opacity=80)}
.modal{position:fixed;top:10%;left:50%;z-index:1050;width:560px;margin-left:-280px;background-color:#fff;border:1px solid #999;border:1px solid rgba(0,0,0,0.3);*border:1px solid #999;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px;-webkit-box-shadow:0 3px 7px rgba(0,0,0,0.3);-moz-box-shadow:0 3px 7px rgba(0,0,0,0.3);box-shadow:0 3px 7px rgba(0,0,0,0.3);-webkit-background-clip:padding-box;-moz-background-clip:padding-box;background-clip:padding-box;outline:none}.modal.fade{-webkit-transition:opacity .3s linear, top .3s ease-out;-moz-transition:opacity .3s linear, top .3s ease-out;-o-transition:opacity .3s linear, top .3s ease-out;transition:opacity .3s linear, top .3s ease-out;top:-25%}
.modal.fade.in{top:10%}
.modal-header{padding:9px 15px;border-bottom:1px solid #eee}.modal-header .close{margin-top:2px}
.modal-header h3{margin:0;line-height:30px}
.modal-body{position:relative;overflow-y:auto;max-height:400px;padding:15px}
.modal-form{margin-bottom:0}
.modal-footer{padding:14px 15px 15px;margin-bottom:0;text-align:right;background-color:#f5f5f5;border-top:1px solid #ddd;-webkit-border-radius:0 0 6px 6px;-moz-border-radius:0 0 6px 6px;border-radius:0 0 6px 6px;-webkit-box-shadow:inset 0 1px 0 #fff;-moz-box-shadow:inset 0 1px 0 #fff;box-shadow:inset 0 1px 0 #fff;*zoom:1}.modal-footer:before,.modal-footer:after{display:table;content:"";line-height:0}
.modal-footer:after{clear:both}
.modal-footer .btn+.btn{margin-left:5px;margin-bottom:0}
.modal-footer .btn-group .btn+.btn{margin-left:-1px}
.modal-footer .btn-block+.btn-block{margin-left:0}
.tooltip{position:absolute;z-index:1030;display:block;visibility:visible;font-size:11px;line-height:1.4;opacity:0;filter:alpha(opacity=0)}.tooltip.in{opacity:.8;filter:alpha(opacity=80)}
.tooltip.top{margin-top:-3px;padding:5px 0}
.tooltip.right{margin-left:3px;padding:0 5px}
.tooltip.bottom{margin-top:3px;padding:5px 0}
.tooltip.left{margin-left:-3px;padding:0 5px}
.tooltip-inner{max-width:200px;padding:8px;color:#fff;text-align:center;text-decoration:none;background-color:#000;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}
.tooltip-arrow{position:absolute;width:0;height:0;border-color:transparent;border-style:solid}
.tooltip.top .tooltip-arrow{bottom:0;left:50%;margin-left:-5px;border-width:5px 5px 0;border-top-color:#000}
.tooltip.right .tooltip-arrow{top:50%;left:0;margin-top:-5px;border-width:5px 5px 5px 0;border-right-color:#000}
.tooltip.left .tooltip-arrow{top:50%;right:0;margin-top:-5px;border-width:5px 0 5px 5px;border-left-color:#000}
.tooltip.bottom .tooltip-arrow{top:0;left:50%;margin-left:-5px;border-width:0 5px 5px;border-bottom-color:#000}
.popover{position:absolute;top:0;left:0;z-index:1010;display:none;max-width:276px;padding:1px;text-align:left;background-color:#fff;-webkit-background-clip:padding-box;-moz-background-clip:padding;background-clip:padding-box;border:1px solid #ccc;border:1px solid rgba(0,0,0,0.2);-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px;-webkit-box-shadow:0 5px 10px rgba(0,0,0,0.2);-moz-box-shadow:0 5px 10px rgba(0,0,0,0.2);box-shadow:0 5px 10px rgba(0,0,0,0.2);white-space:normal}.popover.top{margin-top:-10px}
.popover.right{margin-left:10px}
.popover.bottom{margin-top:10px}
.popover.left{margin-left:-10px}
.popover-title{margin:0;padding:8px 14px;font-size:14px;font-weight:normal;line-height:18px;background-color:#f7f7f7;border-bottom:1px solid #ebebeb;border-radius:5px 5px 0 0;-webkit-border-radius:5px 5px 0 0;-moz-border-radius:5px 5px 0 0;border-radius:5px 5px 0 0}.popover-title:empty{display:none}
.popover-content{padding:9px 14px}
.popover .arrow,.popover .arrow:after{position:absolute;display:block;width:0;height:0;border-color:transparent;border-style:solid}
.popover .arrow{border-width:11px}
.popover .arrow:after{border-width:10px;content:""}
.popover.top .arrow{left:50%;margin-left:-11px;border-bottom-width:0;border-top-color:#999;border-top-color:rgba(0,0,0,0.25);bottom:-11px}.popover.top .arrow:after{bottom:1px;margin-left:-10px;border-bottom-width:0;border-top-color:#fff}
.popover.right .arrow{top:50%;left:-11px;margin-top:-11px;border-left-width:0;border-right-color:#999;border-right-color:rgba(0,0,0,0.25)}.popover.right .arrow:after{left:1px;bottom:-10px;border-left-width:0;border-right-color:#fff}
.popover.bottom .arrow{left:50%;margin-left:-11px;border-top-width:0;border-bottom-color:#999;border-bottom-color:rgba(0,0,0,0.25);top:-11px}.popover.bottom .arrow:after{top:1px;margin-left:-10px;border-top-width:0;border-bottom-color:#fff}
.popover.left .arrow{top:50%;right:-11px;margin-top:-11px;border-right-width:0;border-left-color:#999;border-left-color:rgba(0,0,0,0.25)}.popover.left .arrow:after{right:1px;border-right-width:0;border-left-color:#fff;bottom:-10px}
.thumbnails{margin-left:-20px;list-style:none;*zoom:1}.thumbnails:before,.thumbnails:after{display:table;content:"";line-height:0}
.thumbnails:after{clear:both}
.row-fluid .thumbnails{margin-left:0}
.thumbnails>li{float:left;margin-bottom:20px;margin-left:20px}
.thumbnail{display:block;padding:4px;line-height:20px;border:1px solid #ddd;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px;-webkit-box-shadow:0 1px 3px rgba(0,0,0,0.055);-moz-box-shadow:0 1px 3px rgba(0,0,0,0.055);box-shadow:0 1px 3px rgba(0,0,0,0.055);-webkit-transition:all .2s ease-in-out;-moz-transition:all .2s ease-in-out;-o-transition:all .2s ease-in-out;transition:all .2s ease-in-out}
a.thumbnail:hover,a.thumbnail:focus{border-color:#08c;-webkit-box-shadow:0 1px 4px rgba(0,105,214,0.25);-moz-box-shadow:0 1px 4px rgba(0,105,214,0.25);box-shadow:0 1px 4px rgba(0,105,214,0.25)}
.thumbnail>img{display:block;max-width:100%;margin-left:auto;margin-right:auto}
.thumbnail .caption{padding:9px;color:#555}
.media,.media-body{overflow:hidden;*overflow:visible;zoom:1}
.media,.media .media{margin-top:15px}
.media:first-child{margin-top:0}
.media-object{display:block}
.media-heading{margin:0 0 5px}
.media>.pull-left{margin-right:10px}
.media>.pull-right{margin-left:10px}
.media-list{margin-left:0;list-style:none}
.label,.badge{display:inline-block;padding:2px 4px;font-size:10.998px;font-weight:bold;line-height:14px;color:#fff;vertical-align:baseline;white-space:nowrap;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#999}
.label{border-radius:3px;-webkit-border-radius:3px;-moz-border-radius:3px;border-radius:3px}
.badge{padding-left:9px;padding-right:9px;border-radius:9px;-webkit-border-radius:9px;-moz-border-radius:9px;border-radius:9px}
.label:empty,.badge:empty{display:none}
a.label:hover,a.label:focus,a.badge:hover,a.badge:focus{color:#fff;text-decoration:none;cursor:pointer}
.label-important,.badge-important{background-color:#b94a48}
.label-important[href],.badge-important[href]{background-color:#953b39}
.label-warning,.badge-warning{background-color:#f89406}
.label-warning[href],.badge-warning[href]{background-color:#c67605}
.label-success,.badge-success{background-color:#468847}
.label-success[href],.badge-success[href]{background-color:#356635}
.label-info,.badge-info{background-color:#3a87ad}
.label-info[href],.badge-info[href]{background-color:#2d6987}
.label-inverse,.badge-inverse{background-color:#333}
.label-inverse[href],.badge-inverse[href]{background-color:#1a1a1a}
.btn .label,.btn .badge{position:relative;top:-1px}
.btn-mini .label,.btn-mini .badge{top:0}
@-webkit-keyframes progress-bar-stripes{from{background-position:40px 0} to{background-position:0 0}}@-moz-keyframes progress-bar-stripes{from{background-position:40px 0} to{background-position:0 0}}@-ms-keyframes progress-bar-stripes{from{background-position:40px 0} to{background-position:0 0}}@-o-keyframes progress-bar-stripes{from{background-position:0 0} to{background-position:40px 0}}@keyframes progress-bar-stripes{from{background-position:40px 0} to{background-position:0 0}}.progress{overflow:hidden;height:20px;margin-bottom:20px;background-color:#f7f7f7;background-image:-moz-linear-gradient(top, #f5f5f5, #f9f9f9);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#f5f5f5), to(#f9f9f9));background-image:-webkit-linear-gradient(top, #f5f5f5, #f9f9f9);background-image:-o-linear-gradient(top, #f5f5f5, #f9f9f9);background-image:linear-gradient(to bottom, #f5f5f5, #f9f9f9);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#fff5f5f5', endColorstr='#fff9f9f9', GradientType=0);-webkit-box-shadow:inset 0 1px 2px rgba(0,0,0,0.1);-moz-box-shadow:inset 0 1px 2px rgba(0,0,0,0.1);box-shadow:inset 0 1px 2px rgba(0,0,0,0.1);border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}
.progress .bar{width:0;height:100%;color:#fff;float:left;font-size:12px;text-align:center;text-shadow:0 -1px 0 rgba(0,0,0,0.25);background-color:#0e90d2;background-image:-moz-linear-gradient(top, #149bdf, #0480be);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#149bdf), to(#0480be));background-image:-webkit-linear-gradient(top, #149bdf, #0480be);background-image:-o-linear-gradient(top, #149bdf, #0480be);background-image:linear-gradient(to bottom, #149bdf, #0480be);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff149bdf', endColorstr='#ff0480be', GradientType=0);-webkit-box-shadow:inset 0 -1px 0 rgba(0,0,0,0.15);-moz-box-shadow:inset 0 -1px 0 rgba(0,0,0,0.15);box-shadow:inset 0 -1px 0 rgba(0,0,0,0.15);-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box;-webkit-transition:width .6s ease;-moz-transition:width .6s ease;-o-transition:width .6s ease;transition:width .6s ease}
.progress .bar+.bar{-webkit-box-shadow:inset 1px 0 0 rgba(0,0,0,.15), inset 0 -1px 0 rgba(0,0,0,.15);-moz-box-shadow:inset 1px 0 0 rgba(0,0,0,.15), inset 0 -1px 0 rgba(0,0,0,.15);box-shadow:inset 1px 0 0 rgba(0,0,0,.15), inset 0 -1px 0 rgba(0,0,0,.15)}
.progress-striped .bar{background-color:#149bdf;background-image:-webkit-gradient(linear, 0 100%, 100% 0, color-stop(.25, rgba(255,255,255,0.15)), color-stop(.25, transparent), color-stop(.5, transparent), color-stop(.5, rgba(255,255,255,0.15)), color-stop(.75, rgba(255,255,255,0.15)), color-stop(.75, transparent), to(transparent));background-image:-webkit-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-moz-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-o-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);-webkit-background-size:40px 40px;-moz-background-size:40px 40px;-o-background-size:40px 40px;background-size:40px 40px}
.progress.active .bar{-webkit-animation:progress-bar-stripes 2s linear infinite;-moz-animation:progress-bar-stripes 2s linear infinite;-ms-animation:progress-bar-stripes 2s linear infinite;-o-animation:progress-bar-stripes 2s linear infinite;animation:progress-bar-stripes 2s linear infinite}
.progress-danger .bar,.progress .bar-danger{background-color:#dd514c;background-image:-moz-linear-gradient(top, #ee5f5b, #c43c35);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#ee5f5b), to(#c43c35));background-image:-webkit-linear-gradient(top, #ee5f5b, #c43c35);background-image:-o-linear-gradient(top, #ee5f5b, #c43c35);background-image:linear-gradient(to bottom, #ee5f5b, #c43c35);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffee5f5b', endColorstr='#ffc43c35', GradientType=0)}
.progress-danger.progress-striped .bar,.progress-striped .bar-danger{background-color:#ee5f5b;background-image:-webkit-gradient(linear, 0 100%, 100% 0, color-stop(.25, rgba(255,255,255,0.15)), color-stop(.25, transparent), color-stop(.5, transparent), color-stop(.5, rgba(255,255,255,0.15)), color-stop(.75, rgba(255,255,255,0.15)), color-stop(.75, transparent), to(transparent));background-image:-webkit-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-moz-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-o-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent)}
.progress-success .bar,.progress .bar-success{background-color:#5eb95e;background-image:-moz-linear-gradient(top, #62c462, #57a957);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#62c462), to(#57a957));background-image:-webkit-linear-gradient(top, #62c462, #57a957);background-image:-o-linear-gradient(top, #62c462, #57a957);background-image:linear-gradient(to bottom, #62c462, #57a957);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff62c462', endColorstr='#ff57a957', GradientType=0)}
.progress-success.progress-striped .bar,.progress-striped .bar-success{background-color:#62c462;background-image:-webkit-gradient(linear, 0 100%, 100% 0, color-stop(.25, rgba(255,255,255,0.15)), color-stop(.25, transparent), color-stop(.5, transparent), color-stop(.5, rgba(255,255,255,0.15)), color-stop(.75, rgba(255,255,255,0.15)), color-stop(.75, transparent), to(transparent));background-image:-webkit-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-moz-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-o-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent)}
.progress-info .bar,.progress .bar-info{background-color:#4bb1cf;background-image:-moz-linear-gradient(top, #5bc0de, #339bb9);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#5bc0de), to(#339bb9));background-image:-webkit-linear-gradient(top, #5bc0de, #339bb9);background-image:-o-linear-gradient(top, #5bc0de, #339bb9);background-image:linear-gradient(to bottom, #5bc0de, #339bb9);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ff5bc0de', endColorstr='#ff339bb9', GradientType=0)}
.progress-info.progress-striped .bar,.progress-striped .bar-info{background-color:#5bc0de;background-image:-webkit-gradient(linear, 0 100%, 100% 0, color-stop(.25, rgba(255,255,255,0.15)), color-stop(.25, transparent), color-stop(.5, transparent), color-stop(.5, rgba(255,255,255,0.15)), color-stop(.75, rgba(255,255,255,0.15)), color-stop(.75, transparent), to(transparent));background-image:-webkit-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-moz-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-o-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent)}
.progress-warning .bar,.progress .bar-warning{background-color:#faa732;background-image:-moz-linear-gradient(top, #fbb450, #f89406);background-image:-webkit-gradient(linear, 0 0, 0 100%, from(#fbb450), to(#f89406));background-image:-webkit-linear-gradient(top, #fbb450, #f89406);background-image:-o-linear-gradient(top, #fbb450, #f89406);background-image:linear-gradient(to bottom, #fbb450, #f89406);background-repeat:repeat-x;filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#fffbb450', endColorstr='#fff89406', GradientType=0)}
.progress-warning.progress-striped .bar,.progress-striped .bar-warning{background-color:#fbb450;background-image:-webkit-gradient(linear, 0 100%, 100% 0, color-stop(.25, rgba(255,255,255,0.15)), color-stop(.25, transparent), color-stop(.5, transparent), color-stop(.5, rgba(255,255,255,0.15)), color-stop(.75, rgba(255,255,255,0.15)), color-stop(.75, transparent), to(transparent));background-image:-webkit-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-moz-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:-o-linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent);background-image:linear-gradient(45deg, rgba(255,255,255,0.15) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.15) 50%, rgba(255,255,255,0.15) 75%, transparent 75%, transparent)}
.accordion{margin-bottom:20px}
.accordion-group{margin-bottom:2px;border:1px solid #e5e5e5;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}
.accordion-heading{border-bottom:0}
.accordion-heading .accordion-toggle{display:block;padding:8px 15px}
.accordion-toggle{cursor:pointer}
.accordion-inner{padding:9px 15px;border-top:1px solid #e5e5e5}
.carousel{position:relative;margin-bottom:20px;line-height:1}
.carousel-inner{overflow:hidden;width:100%;position:relative}
.carousel-inner>.item{display:none;position:relative;-webkit-transition:.6s ease-in-out left;-moz-transition:.6s ease-in-out left;-o-transition:.6s ease-in-out left;transition:.6s ease-in-out left}.carousel-inner>.item>img,.carousel-inner>.item>a>img{display:block;line-height:1}
.carousel-inner>.active,.carousel-inner>.next,.carousel-inner>.prev{display:block}
.carousel-inner>.active{left:0}
.carousel-inner>.next,.carousel-inner>.prev{position:absolute;top:0;width:100%}
.carousel-inner>.next{left:100%}
.carousel-inner>.prev{left:-100%}
.carousel-inner>.next.left,.carousel-inner>.prev.right{left:0}
.carousel-inner>.active.left{left:-100%}
.carousel-inner>.active.right{left:100%}
.carousel-control{position:absolute;top:40%;left:15px;width:40px;height:40px;margin-top:-20px;font-size:60px;font-weight:100;line-height:30px;color:#fff;text-align:center;background:#222;border:3px solid #fff;-webkit-border-radius:23px;-moz-border-radius:23px;border-radius:23px;opacity:.5;filter:alpha(opacity=50)}.carousel-control.right{left:auto;right:15px}
.carousel-control:hover,.carousel-control:focus{color:#fff;text-decoration:none;opacity:.9;filter:alpha(opacity=90)}
.carousel-indicators{position:absolute;top:15px;right:15px;z-index:5;margin:0;list-style:none}.carousel-indicators li{display:block;float:left;width:10px;height:10px;margin-left:5px;text-indent:-999px;background-color:#ccc;background-color:rgba(255,255,255,0.25);border-radius:5px}
.carousel-indicators .active{background-color:#fff}
.carousel-caption{position:absolute;left:0;right:0;bottom:0;padding:15px;background:#333;background:rgba(0,0,0,0.75)}
.carousel-caption h4,.carousel-caption p{color:#fff;line-height:20px}
.carousel-caption h4{margin:0 0 5px}
.carousel-caption p{margin-bottom:0}
.hero-unit{padding:60px;margin-bottom:30px;font-size:18px;font-weight:200;line-height:30px;color:inherit;background-color:#eee;border-radius:6px;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px}.hero-unit h1{margin-bottom:0;font-size:60px;line-height:1;color:inherit;letter-spacing:-1px}
.hero-unit li{line-height:30px}
.pull-right{float:right}
.pull-left{float:left}
.hide{display:none}
.show{display:block}
.invisible{visibility:hidden}
.affix{position:fixed}
@-ms-viewport{width:device-width}.hidden{display:none;visibility:hidden}
.visible-phone{display:none !important}
.visible-tablet{display:none !important}
.hidden-desktop{display:none !important}
.visible-desktop{display:inherit !important}
@media (min-width:768px) and (max-width:979px){.hidden-desktop{display:inherit !important} .visible-desktop{display:none !important} .visible-tablet{display:inherit !important} .hidden-tablet{display:none !important}}@media (max-width:767px){.hidden-desktop{display:inherit !important} .visible-desktop{display:none !important} .visible-phone{display:inherit !important} .hidden-phone{display:none !important}}.visible-print{display:none !important}
@media print{.visible-print{display:inherit !important} .hidden-print{display:none !important}}@media (min-width:1200px){.row{margin-left:-30px;*zoom:1}.row:before,.row:after{display:table;content:"";line-height:0} .row:after{clear:both} [class*="span"]{float:left;min-height:1px;margin-left:30px} .container,.navbar-static-top .container,.navbar-fixed-top .container,.navbar-fixed-bottom .container{width:1170px} .span12{width:1170px} .span11{width:1070px} .span10{width:970px} .span9{width:870px} .span8{width:770px} .span7{width:670px} .span6{width:570px} .span5{width:470px} .span4{width:370px} .span3{width:270px} .span2{width:170px} .span1{width:70px} .offset12{margin-left:1230px} .offset11{margin-left:1130px} .offset10{margin-left:1030px} .offset9{margin-left:930px} .offset8{margin-left:830px} .offset7{margin-left:730px} .offset6{margin-left:630px} .offset5{margin-left:530px} .offset4{margin-left:430px} .offset3{margin-left:330px} .offset2{margin-left:230px} .offset1{margin-left:130px} .row-fluid{width:100%;*zoom:1}.row-fluid:before,.row-fluid:after{display:table;content:"";line-height:0} .row-fluid:after{clear:both} .row-fluid [class*="span"]{display:block;width:100%;min-height:30px;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box;float:left;margin-left:2.564102564102564%;*margin-left:2.5109110747408616%} .row-fluid [class*="span"]:first-child{margin-left:0} .row-fluid .controls-row [class*="span"]+[class*="span"]{margin-left:2.564102564102564%} .row-fluid .span12{width:100%;*width:99.94680851063829%} .row-fluid .span11{width:91.45299145299145%;*width:91.39979996362975%} .row-fluid .span10{width:82.90598290598291%;*width:82.8527914166212%} .row-fluid .span9{width:74.35897435897436%;*width:74.30578286961266%} .row-fluid .span8{width:65.81196581196582%;*width:65.75877432260411%} .row-fluid .span7{width:57.26495726495726%;*width:57.21176577559556%} .row-fluid .span6{width:48.717948717948715%;*width:48.664757228587014%} .row-fluid .span5{width:40.17094017094017%;*width:40.11774868157847%} .row-fluid .span4{width:31.623931623931625%;*width:31.570740134569924%} .row-fluid .span3{width:23.076923076923077%;*width:23.023731587561375%} .row-fluid .span2{width:14.52991452991453%;*width:14.476723040552828%} .row-fluid .span1{width:5.982905982905983%;*width:5.929714493544281%} .row-fluid .offset12{margin-left:105.12820512820512%;*margin-left:105.02182214948171%} .row-fluid .offset12:first-child{margin-left:102.56410256410257%;*margin-left:102.45771958537915%} .row-fluid .offset11{margin-left:96.58119658119658%;*margin-left:96.47481360247316%} .row-fluid .offset11:first-child{margin-left:94.01709401709402%;*margin-left:93.91071103837061%} .row-fluid .offset10{margin-left:88.03418803418803%;*margin-left:87.92780505546462%} .row-fluid .offset10:first-child{margin-left:85.47008547008548%;*margin-left:85.36370249136206%} .row-fluid .offset9{margin-left:79.48717948717949%;*margin-left:79.38079650845607%} .row-fluid .offset9:first-child{margin-left:76.92307692307693%;*margin-left:76.81669394435352%} .row-fluid .offset8{margin-left:70.94017094017094%;*margin-left:70.83378796144753%} .row-fluid .offset8:first-child{margin-left:68.37606837606839%;*margin-left:68.26968539734497%} .row-fluid .offset7{margin-left:62.393162393162385%;*margin-left:62.28677941443899%} .row-fluid .offset7:first-child{margin-left:59.82905982905982%;*margin-left:59.72267685033642%} .row-fluid .offset6{margin-left:53.84615384615384%;*margin-left:53.739770867430444%} .row-fluid .offset6:first-child{margin-left:51.28205128205128%;*margin-left:51.175668303327875%} .row-fluid .offset5{margin-left:45.299145299145295%;*margin-left:45.1927623204219%} .row-fluid .offset5:first-child{margin-left:42.73504273504273%;*margin-left:42.62865975631933%} .row-fluid .offset4{margin-left:36.75213675213675%;*margin-left:36.645753773413354%} .row-fluid .offset4:first-child{margin-left:34.18803418803419%;*margin-left:34.081651209310785%} .row-fluid .offset3{margin-left:28.205128205128204%;*margin-left:28.0987452264048%} .row-fluid .offset3:first-child{margin-left:25.641025641025642%;*margin-left:25.53464266230224%} .row-fluid .offset2{margin-left:19.65811965811966%;*margin-left:19.551736679396257%} .row-fluid .offset2:first-child{margin-left:17.094017094017094%;*margin-left:16.98763411529369%} .row-fluid .offset1{margin-left:11.11111111111111%;*margin-left:11.004728132387708%} .row-fluid .offset1:first-child{margin-left:8.547008547008547%;*margin-left:8.440625568285142%} input,textarea,.uneditable-input{margin-left:0} .controls-row [class*="span"]+[class*="span"]{margin-left:30px} input.span12,textarea.span12,.uneditable-input.span12{width:1156px} input.span11,textarea.span11,.uneditable-input.span11{width:1056px} input.span10,textarea.span10,.uneditable-input.span10{width:956px} input.span9,textarea.span9,.uneditable-input.span9{width:856px} input.span8,textarea.span8,.uneditable-input.span8{width:756px} input.span7,textarea.span7,.uneditable-input.span7{width:656px} input.span6,textarea.span6,.uneditable-input.span6{width:556px} input.span5,textarea.span5,.uneditable-input.span5{width:456px} input.span4,textarea.span4,.uneditable-input.span4{width:356px} input.span3,textarea.span3,.uneditable-input.span3{width:256px} input.span2,textarea.span2,.uneditable-input.span2{width:156px} input.span1,textarea.span1,.uneditable-input.span1{width:56px} .thumbnails{margin-left:-30px} .thumbnails>li{margin-left:30px} .row-fluid .thumbnails{margin-left:0}}@media (min-width:768px) and (max-width:979px){.row{margin-left:-20px;*zoom:1}.row:before,.row:after{display:table;content:"";line-height:0} .row:after{clear:both} [class*="span"]{float:left;min-height:1px;margin-left:20px} .container,.navbar-static-top .container,.navbar-fixed-top .container,.navbar-fixed-bottom .container{width:724px} .span12{width:724px} .span11{width:662px} .span10{width:600px} .span9{width:538px} .span8{width:476px} .span7{width:414px} .span6{width:352px} .span5{width:290px} .span4{width:228px} .span3{width:166px} .span2{width:104px} .span1{width:42px} .offset12{margin-left:764px} .offset11{margin-left:702px} .offset10{margin-left:640px} .offset9{margin-left:578px} .offset8{margin-left:516px} .offset7{margin-left:454px} .offset6{margin-left:392px} .offset5{margin-left:330px} .offset4{margin-left:268px} .offset3{margin-left:206px} .offset2{margin-left:144px} .offset1{margin-left:82px} .row-fluid{width:100%;*zoom:1}.row-fluid:before,.row-fluid:after{display:table;content:"";line-height:0} .row-fluid:after{clear:both} .row-fluid [class*="span"]{display:block;width:100%;min-height:30px;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box;float:left;margin-left:2.7624309392265194%;*margin-left:2.709239449864817%} .row-fluid [class*="span"]:first-child{margin-left:0} .row-fluid .controls-row [class*="span"]+[class*="span"]{margin-left:2.7624309392265194%} .row-fluid .span12{width:100%;*width:99.94680851063829%} .row-fluid .span11{width:91.43646408839778%;*width:91.38327259903608%} .row-fluid .span10{width:82.87292817679558%;*width:82.81973668743387%} .row-fluid .span9{width:74.30939226519337%;*width:74.25620077583166%} .row-fluid .span8{width:65.74585635359117%;*width:65.69266486422946%} .row-fluid .span7{width:57.18232044198895%;*width:57.12912895262725%} .row-fluid .span6{width:48.61878453038674%;*width:48.56559304102504%} .row-fluid .span5{width:40.05524861878453%;*width:40.00205712942283%} .row-fluid .span4{width:31.491712707182323%;*width:31.43852121782062%} .row-fluid .span3{width:22.92817679558011%;*width:22.87498530621841%} .row-fluid .span2{width:14.3646408839779%;*width:14.311449394616199%} .row-fluid .span1{width:5.801104972375691%;*width:5.747913483013988%} .row-fluid .offset12{margin-left:105.52486187845304%;*margin-left:105.41847889972962%} .row-fluid .offset12:first-child{margin-left:102.76243093922652%;*margin-left:102.6560479605031%} .row-fluid .offset11{margin-left:96.96132596685082%;*margin-left:96.8549429881274%} .row-fluid .offset11:first-child{margin-left:94.1988950276243%;*margin-left:94.09251204890089%} .row-fluid .offset10{margin-left:88.39779005524862%;*margin-left:88.2914070765252%} .row-fluid .offset10:first-child{margin-left:85.6353591160221%;*margin-left:85.52897613729868%} .row-fluid .offset9{margin-left:79.8342541436464%;*margin-left:79.72787116492299%} .row-fluid .offset9:first-child{margin-left:77.07182320441989%;*margin-left:76.96544022569647%} .row-fluid .offset8{margin-left:71.2707182320442%;*margin-left:71.16433525332079%} .row-fluid .offset8:first-child{margin-left:68.50828729281768%;*margin-left:68.40190431409427%} .row-fluid .offset7{margin-left:62.70718232044199%;*margin-left:62.600799341718584%} .row-fluid .offset7:first-child{margin-left:59.94475138121547%;*margin-left:59.838368402492065%} .row-fluid .offset6{margin-left:54.14364640883978%;*margin-left:54.037263430116376%} .row-fluid .offset6:first-child{margin-left:51.38121546961326%;*margin-left:51.27483249088986%} .row-fluid .offset5{margin-left:45.58011049723757%;*margin-left:45.47372751851417%} .row-fluid .offset5:first-child{margin-left:42.81767955801105%;*margin-left:42.71129657928765%} .row-fluid .offset4{margin-left:37.01657458563536%;*margin-left:36.91019160691196%} .row-fluid .offset4:first-child{margin-left:34.25414364640884%;*margin-left:34.14776066768544%} .row-fluid .offset3{margin-left:28.45303867403315%;*margin-left:28.346655695309746%} .row-fluid .offset3:first-child{margin-left:25.69060773480663%;*margin-left:25.584224756083227%} .row-fluid .offset2{margin-left:19.88950276243094%;*margin-left:19.783119783707537%} .row-fluid .offset2:first-child{margin-left:17.12707182320442%;*margin-left:17.02068884448102%} .row-fluid .offset1{margin-left:11.32596685082873%;*margin-left:11.219583872105325%} .row-fluid .offset1:first-child{margin-left:8.56353591160221%;*margin-left:8.457152932878806%} input,textarea,.uneditable-input{margin-left:0} .controls-row [class*="span"]+[class*="span"]{margin-left:20px} input.span12,textarea.span12,.uneditable-input.span12{width:710px} input.span11,textarea.span11,.uneditable-input.span11{width:648px} input.span10,textarea.span10,.uneditable-input.span10{width:586px} input.span9,textarea.span9,.uneditable-input.span9{width:524px} input.span8,textarea.span8,.uneditable-input.span8{width:462px} input.span7,textarea.span7,.uneditable-input.span7{width:400px} input.span6,textarea.span6,.uneditable-input.span6{width:338px} input.span5,textarea.span5,.uneditable-input.span5{width:276px} input.span4,textarea.span4,.uneditable-input.span4{width:214px} input.span3,textarea.span3,.uneditable-input.span3{width:152px} input.span2,textarea.span2,.uneditable-input.span2{width:90px} input.span1,textarea.span1,.uneditable-input.span1{width:28px}}@media (max-width:767px){body{padding-left:20px;padding-right:20px} .navbar-fixed-top,.navbar-fixed-bottom,.navbar-static-top{margin-left:-20px;margin-right:-20px} .container-fluid{padding:0} .dl-horizontal dt{float:none;clear:none;width:auto;text-align:left} .dl-horizontal dd{margin-left:0} .container{width:auto} .row-fluid{width:100%} .row,.thumbnails{margin-left:0} .thumbnails>li{float:none;margin-left:0} [class*="span"],.uneditable-input[class*="span"],.row-fluid [class*="span"]{float:none;display:block;width:100%;margin-left:0;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box} .span12,.row-fluid .span12{width:100%;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box} .row-fluid [class*="offset"]:first-child{margin-left:0} .input-large,.input-xlarge,.input-xxlarge,input[class*="span"],select[class*="span"],textarea[class*="span"],.uneditable-input{display:block;width:100%;min-height:30px;-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box} .input-prepend input,.input-append input,.input-prepend input[class*="span"],.input-append input[class*="span"]{display:inline-block;width:auto} .controls-row [class*="span"]+[class*="span"]{margin-left:0} .modal{position:fixed;top:20px;left:20px;right:20px;width:auto;margin:0}.modal.fade{top:-100px} .modal.fade.in{top:20px}}@media (max-width:480px){.nav-collapse{-webkit-transform:translate3d(0, 0, 0)} .page-header h1 small{display:block;line-height:20px} input[type="checkbox"],input[type="radio"]{border:1px solid #ccc} .form-horizontal .control-label{float:none;width:auto;padding-top:0;text-align:left} .form-horizontal .controls{margin-left:0} .form-horizontal .control-list{padding-top:0} .form-horizontal .form-actions{padding-left:10px;padding-right:10px} .media .pull-left,.media .pull-right{float:none;display:block;margin-bottom:10px} .media-object{margin-right:0;margin-left:0} .modal{top:10px;left:10px;right:10px} .modal-header .close{padding:10px;margin:-10px} .carousel-caption{position:static}}@media (max-width:979px){body{padding-top:0} .navbar-fixed-top,.navbar-fixed-bottom{position:static} .navbar-fixed-top{margin-bottom:20px} .navbar-fixed-bottom{margin-top:20px} .navbar-fixed-top .navbar-inner,.navbar-fixed-bottom .navbar-inner{padding:5px} .navbar .container{width:auto;padding:0} .navbar .brand{padding-left:10px;padding-right:10px;margin:0 0 0 -5px} .nav-collapse{clear:both} .nav-collapse .nav{float:none;margin:0 0 10px} .nav-collapse .nav>li{float:none} .nav-collapse .nav>li>a{margin-bottom:2px} .nav-collapse .nav>.divider-vertical{display:none} .nav-collapse .nav .nav-header{color:#777;text-shadow:none} .nav-collapse .nav>li>a,.nav-collapse .dropdown-menu a{padding:9px 15px;font-weight:bold;color:#777;border-radius:3px;-webkit-border-radius:3px;-moz-border-radius:3px;border-radius:3px} .nav-collapse .btn{padding:4px 10px 4px;font-weight:normal;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px} .nav-collapse .dropdown-menu li+li a{margin-bottom:2px} .nav-collapse .nav>li>a:hover,.nav-collapse .nav>li>a:focus,.nav-collapse .dropdown-menu a:hover,.nav-collapse .dropdown-menu a:focus{background-color:#f2f2f2} .navbar-inverse .nav-collapse .nav>li>a,.navbar-inverse .nav-collapse .dropdown-menu a{color:#999} .navbar-inverse .nav-collapse .nav>li>a:hover,.navbar-inverse .nav-collapse .nav>li>a:focus,.navbar-inverse .nav-collapse .dropdown-menu a:hover,.navbar-inverse .nav-collapse .dropdown-menu a:focus{background-color:#111} .nav-collapse.in .btn-group{margin-top:5px;padding:0} .nav-collapse .dropdown-menu{position:static;top:auto;left:auto;float:none;display:none;max-width:none;margin:0 15px;padding:0;background-color:transparent;border:none;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0;-webkit-box-shadow:none;-moz-box-shadow:none;box-shadow:none} .nav-collapse .open>.dropdown-menu{display:block} .nav-collapse .dropdown-menu:before,.nav-collapse .dropdown-menu:after{display:none} .nav-collapse .dropdown-menu .divider{display:none} .nav-collapse .nav>li>.dropdown-menu:before,.nav-collapse .nav>li>.dropdown-menu:after{display:none} .nav-collapse .navbar-form,.nav-collapse .navbar-search{float:none;padding:10px 15px;margin:10px 0;border-top:1px solid #f2f2f2;border-bottom:1px solid #f2f2f2;-webkit-box-shadow:inset 0 1px 0 rgba(255,255,255,.1), 0 1px 0 rgba(255,255,255,.1);-moz-box-shadow:inset 0 1px 0 rgba(255,255,255,.1), 0 1px 0 rgba(255,255,255,.1);box-shadow:inset 0 1px 0 rgba(255,255,255,.1), 0 1px 0 rgba(255,255,255,.1)} .navbar-inverse .nav-collapse .navbar-form,.navbar-inverse .nav-collapse .navbar-search{border-top-color:#111;border-bottom-color:#111} .navbar .nav-collapse .nav.pull-right{float:none;margin-left:0} .nav-collapse,.nav-collapse.collapse{overflow:hidden;height:0} .navbar .btn-navbar{display:block} .navbar-static .navbar-inner{padding-left:10px;padding-right:10px}}@media (min-width:979px + 1){.nav-collapse.collapse{height:auto !important;overflow:visible !important}}@font-face{font-family:'FontAwesome';src:url('../components/font-awesome/font/fontawesome-webfont.eot?v=3.2.1');src:url('../components/font-awesome/font/fontawesome-webfont.eot?#iefix&v=3.2.1') format('embedded-opentype'),url('../components/font-awesome/font/fontawesome-webfont.woff?v=3.2.1') format('woff'),url('../components/font-awesome/font/fontawesome-webfont.ttf?v=3.2.1') format('truetype'),url('../components/font-awesome/font/fontawesome-webfont.svg#fontawesomeregular?v=3.2.1') format('svg');font-weight:normal;font-style:normal}[class^="icon-"],[class*=" icon-"]{font-family:FontAwesome;font-weight:normal;font-style:normal;text-decoration:inherit;-webkit-font-smoothing:antialiased;*margin-right:.3em}
[class^="icon-"]:before,[class*=" icon-"]:before{text-decoration:inherit;display:inline-block;speak:none}
.icon-large:before{vertical-align:-10%;font-size:1.3333333333333333em}
a [class^="icon-"],a [class*=" icon-"]{display:inline}
[class^="icon-"].icon-fixed-width,[class*=" icon-"].icon-fixed-width{display:inline-block;width:1.1428571428571428em;text-align:right;padding-right:.2857142857142857em}[class^="icon-"].icon-fixed-width.icon-large,[class*=" icon-"].icon-fixed-width.icon-large{width:1.4285714285714286em}
.icons-ul{margin-left:2.142857142857143em;list-style-type:none}.icons-ul>li{position:relative}
.icons-ul .icon-li{position:absolute;left:-2.142857142857143em;width:2.142857142857143em;text-align:center;line-height:inherit}
[class^="icon-"].hide,[class*=" icon-"].hide{display:none}
.icon-muted{color:#eee}
.icon-light{color:#fff}
.icon-dark{color:#333}
.icon-border{border:solid 1px #eee;padding:.2em .25em .15em;border-radius:3px;-webkit-border-radius:3px;-moz-border-radius:3px;border-radius:3px}
.icon-2x{font-size:2em}.icon-2x.icon-border{border-width:2px;border-radius:4px;-webkit-border-radius:4px;-moz-border-radius:4px;border-radius:4px}
.icon-3x{font-size:3em}.icon-3x.icon-border{border-width:3px;border-radius:5px;-webkit-border-radius:5px;-moz-border-radius:5px;border-radius:5px}
.icon-4x{font-size:4em}.icon-4x.icon-border{border-width:4px;border-radius:6px;-webkit-border-radius:6px;-moz-border-radius:6px;border-radius:6px}
.icon-5x{font-size:5em}.icon-5x.icon-border{border-width:5px;border-radius:7px;-webkit-border-radius:7px;-moz-border-radius:7px;border-radius:7px}
.pull-right{float:right}
.pull-left{float:left}
[class^="icon-"].pull-left,[class*=" icon-"].pull-left{margin-right:.3em}
[class^="icon-"].pull-right,[class*=" icon-"].pull-right{margin-left:.3em}
[class^="icon-"],[class*=" icon-"]{display:inline;width:auto;height:auto;line-height:normal;vertical-align:baseline;background-image:none;background-position:0 0;background-repeat:repeat;margin-top:0}
.icon-white,.nav-pills>.active>a>[class^="icon-"],.nav-pills>.active>a>[class*=" icon-"],.nav-list>.active>a>[class^="icon-"],.nav-list>.active>a>[class*=" icon-"],.navbar-inverse .nav>.active>a>[class^="icon-"],.navbar-inverse .nav>.active>a>[class*=" icon-"],.dropdown-menu>li>a:hover>[class^="icon-"],.dropdown-menu>li>a:hover>[class*=" icon-"],.dropdown-menu>.active>a>[class^="icon-"],.dropdown-menu>.active>a>[class*=" icon-"],.dropdown-submenu:hover>a>[class^="icon-"],.dropdown-submenu:hover>a>[class*=" icon-"]{background-image:none}
.btn [class^="icon-"].icon-large,.nav [class^="icon-"].icon-large,.btn [class*=" icon-"].icon-large,.nav [class*=" icon-"].icon-large{line-height:.9em}
.btn [class^="icon-"].icon-spin,.nav [class^="icon-"].icon-spin,.btn [class*=" icon-"].icon-spin,.nav [class*=" icon-"].icon-spin{display:inline-block}
.nav-tabs [class^="icon-"],.nav-pills [class^="icon-"],.nav-tabs [class*=" icon-"],.nav-pills [class*=" icon-"],.nav-tabs [class^="icon-"].icon-large,.nav-pills [class^="icon-"].icon-large,.nav-tabs [class*=" icon-"].icon-large,.nav-pills [class*=" icon-"].icon-large{line-height:.9em}
.btn [class^="icon-"].pull-left.icon-2x,.btn [class*=" icon-"].pull-left.icon-2x,.btn [class^="icon-"].pull-right.icon-2x,.btn [class*=" icon-"].pull-right.icon-2x{margin-top:.18em}
.btn [class^="icon-"].icon-spin.icon-large,.btn [class*=" icon-"].icon-spin.icon-large{line-height:.8em}
.btn.btn-small [class^="icon-"].pull-left.icon-2x,.btn.btn-small [class*=" icon-"].pull-left.icon-2x,.btn.btn-small [class^="icon-"].pull-right.icon-2x,.btn.btn-small [class*=" icon-"].pull-right.icon-2x{margin-top:.25em}
.btn.btn-large [class^="icon-"],.btn.btn-large [class*=" icon-"]{margin-top:0}.btn.btn-large [class^="icon-"].pull-left.icon-2x,.btn.btn-large [class*=" icon-"].pull-left.icon-2x,.btn.btn-large [class^="icon-"].pull-right.icon-2x,.btn.btn-large [class*=" icon-"].pull-right.icon-2x{margin-top:.05em}
.btn.btn-large [class^="icon-"].pull-left.icon-2x,.btn.btn-large [class*=" icon-"].pull-left.icon-2x{margin-right:.2em}
.btn.btn-large [class^="icon-"].pull-right.icon-2x,.btn.btn-large [class*=" icon-"].pull-right.icon-2x{margin-left:.2em}
.nav-list [class^="icon-"],.nav-list [class*=" icon-"]{line-height:inherit}
.icon-stack{position:relative;display:inline-block;width:2em;height:2em;line-height:2em;vertical-align:-35%}.icon-stack [class^="icon-"],.icon-stack [class*=" icon-"]{display:block;text-align:center;position:absolute;width:100%;height:100%;font-size:1em;line-height:inherit;*line-height:2em}
.icon-stack .icon-stack-base{font-size:2em;*line-height:1em}
.icon-spin{display:inline-block;-moz-animation:spin 2s infinite linear;-o-animation:spin 2s infinite linear;-webkit-animation:spin 2s infinite linear;animation:spin 2s infinite linear}
a .icon-stack,a .icon-spin{display:inline-block;text-decoration:none}
@-moz-keyframes spin{0%{-moz-transform:rotate(0deg)} 100%{-moz-transform:rotate(359deg)}}@-webkit-keyframes spin{0%{-webkit-transform:rotate(0deg)} 100%{-webkit-transform:rotate(359deg)}}@-o-keyframes spin{0%{-o-transform:rotate(0deg)} 100%{-o-transform:rotate(359deg)}}@-ms-keyframes spin{0%{-ms-transform:rotate(0deg)} 100%{-ms-transform:rotate(359deg)}}@keyframes spin{0%{transform:rotate(0deg)} 100%{transform:rotate(359deg)}}.icon-rotate-90:before{-webkit-transform:rotate(90deg);-moz-transform:rotate(90deg);-ms-transform:rotate(90deg);-o-transform:rotate(90deg);transform:rotate(90deg);filter:progid:DXImageTransform.Microsoft.BasicImage(rotation=1)}
.icon-rotate-180:before{-webkit-transform:rotate(180deg);-moz-transform:rotate(180deg);-ms-transform:rotate(180deg);-o-transform:rotate(180deg);transform:rotate(180deg);filter:progid:DXImageTransform.Microsoft.BasicImage(rotation=2)}
.icon-rotate-270:before{-webkit-transform:rotate(270deg);-moz-transform:rotate(270deg);-ms-transform:rotate(270deg);-o-transform:rotate(270deg);transform:rotate(270deg);filter:progid:DXImageTransform.Microsoft.BasicImage(rotation=3)}
.icon-flip-horizontal:before{-webkit-transform:scale(-1, 1);-moz-transform:scale(-1, 1);-ms-transform:scale(-1, 1);-o-transform:scale(-1, 1);transform:scale(-1, 1)}
.icon-flip-vertical:before{-webkit-transform:scale(1, -1);-moz-transform:scale(1, -1);-ms-transform:scale(1, -1);-o-transform:scale(1, -1);transform:scale(1, -1)}
a .icon-rotate-90:before,a .icon-rotate-180:before,a .icon-rotate-270:before,a .icon-flip-horizontal:before,a .icon-flip-vertical:before{display:inline-block}
.icon-glass:before{content:"\f000"}
.icon-music:before{content:"\f001"}
.icon-search:before{content:"\f002"}
.icon-envelope-alt:before{content:"\f003"}
.icon-heart:before{content:"\f004"}
.icon-star:before{content:"\f005"}
.icon-star-empty:before{content:"\f006"}
.icon-user:before{content:"\f007"}
.icon-film:before{content:"\f008"}
.icon-th-large:before{content:"\f009"}
.icon-th:before{content:"\f00a"}
.icon-th-list:before{content:"\f00b"}
.icon-ok:before{content:"\f00c"}
.icon-remove:before{content:"\f00d"}
.icon-zoom-in:before{content:"\f00e"}
.icon-zoom-out:before{content:"\f010"}
.icon-power-off:before,.icon-off:before{content:"\f011"}
.icon-signal:before{content:"\f012"}
.icon-gear:before,.icon-cog:before{content:"\f013"}
.icon-trash:before{content:"\f014"}
.icon-home:before{content:"\f015"}
.icon-file-alt:before{content:"\f016"}
.icon-time:before{content:"\f017"}
.icon-road:before{content:"\f018"}
.icon-download-alt:before{content:"\f019"}
.icon-download:before{content:"\f01a"}
.icon-upload:before{content:"\f01b"}
.icon-inbox:before{content:"\f01c"}
.icon-play-circle:before{content:"\f01d"}
.icon-rotate-right:before,.icon-repeat:before{content:"\f01e"}
.icon-refresh:before{content:"\f021"}
.icon-list-alt:before{content:"\f022"}
.icon-lock:before{content:"\f023"}
.icon-flag:before{content:"\f024"}
.icon-headphones:before{content:"\f025"}
.icon-volume-off:before{content:"\f026"}
.icon-volume-down:before{content:"\f027"}
.icon-volume-up:before{content:"\f028"}
.icon-qrcode:before{content:"\f029"}
.icon-barcode:before{content:"\f02a"}
.icon-tag:before{content:"\f02b"}
.icon-tags:before{content:"\f02c"}
.icon-book:before{content:"\f02d"}
.icon-bookmark:before{content:"\f02e"}
.icon-print:before{content:"\f02f"}
.icon-camera:before{content:"\f030"}
.icon-font:before{content:"\f031"}
.icon-bold:before{content:"\f032"}
.icon-italic:before{content:"\f033"}
.icon-text-height:before{content:"\f034"}
.icon-text-width:before{content:"\f035"}
.icon-align-left:before{content:"\f036"}
.icon-align-center:before{content:"\f037"}
.icon-align-right:before{content:"\f038"}
.icon-align-justify:before{content:"\f039"}
.icon-list:before{content:"\f03a"}
.icon-indent-left:before{content:"\f03b"}
.icon-indent-right:before{content:"\f03c"}
.icon-facetime-video:before{content:"\f03d"}
.icon-picture:before{content:"\f03e"}
.icon-pencil:before{content:"\f040"}
.icon-map-marker:before{content:"\f041"}
.icon-adjust:before{content:"\f042"}
.icon-tint:before{content:"\f043"}
.icon-edit:before{content:"\f044"}
.icon-share:before{content:"\f045"}
.icon-check:before{content:"\f046"}
.icon-move:before{content:"\f047"}
.icon-step-backward:before{content:"\f048"}
.icon-fast-backward:before{content:"\f049"}
.icon-backward:before{content:"\f04a"}
.icon-play:before{content:"\f04b"}
.icon-pause:before{content:"\f04c"}
.icon-stop:before{content:"\f04d"}
.icon-forward:before{content:"\f04e"}
.icon-fast-forward:before{content:"\f050"}
.icon-step-forward:before{content:"\f051"}
.icon-eject:before{content:"\f052"}
.icon-chevron-left:before{content:"\f053"}
.icon-chevron-right:before{content:"\f054"}
.icon-plus-sign:before{content:"\f055"}
.icon-minus-sign:before{content:"\f056"}
.icon-remove-sign:before{content:"\f057"}
.icon-ok-sign:before{content:"\f058"}
.icon-question-sign:before{content:"\f059"}
.icon-info-sign:before{content:"\f05a"}
.icon-screenshot:before{content:"\f05b"}
.icon-remove-circle:before{content:"\f05c"}
.icon-ok-circle:before{content:"\f05d"}
.icon-ban-circle:before{content:"\f05e"}
.icon-arrow-left:before{content:"\f060"}
.icon-arrow-right:before{content:"\f061"}
.icon-arrow-up:before{content:"\f062"}
.icon-arrow-down:before{content:"\f063"}
.icon-mail-forward:before,.icon-share-alt:before{content:"\f064"}
.icon-resize-full:before{content:"\f065"}
.icon-resize-small:before{content:"\f066"}
.icon-plus:before{content:"\f067"}
.icon-minus:before{content:"\f068"}
.icon-asterisk:before{content:"\f069"}
.icon-exclamation-sign:before{content:"\f06a"}
.icon-gift:before{content:"\f06b"}
.icon-leaf:before{content:"\f06c"}
.icon-fire:before{content:"\f06d"}
.icon-eye-open:before{content:"\f06e"}
.icon-eye-close:before{content:"\f070"}
.icon-warning-sign:before{content:"\f071"}
.icon-plane:before{content:"\f072"}
.icon-calendar:before{content:"\f073"}
.icon-random:before{content:"\f074"}
.icon-comment:before{content:"\f075"}
.icon-magnet:before{content:"\f076"}
.icon-chevron-up:before{content:"\f077"}
.icon-chevron-down:before{content:"\f078"}
.icon-retweet:before{content:"\f079"}
.icon-shopping-cart:before{content:"\f07a"}
.icon-folder-close:before{content:"\f07b"}
.icon-folder-open:before{content:"\f07c"}
.icon-resize-vertical:before{content:"\f07d"}
.icon-resize-horizontal:before{content:"\f07e"}
.icon-bar-chart:before{content:"\f080"}
.icon-twitter-sign:before{content:"\f081"}
.icon-facebook-sign:before{content:"\f082"}
.icon-camera-retro:before{content:"\f083"}
.icon-key:before{content:"\f084"}
.icon-gears:before,.icon-cogs:before{content:"\f085"}
.icon-comments:before{content:"\f086"}
.icon-thumbs-up-alt:before{content:"\f087"}
.icon-thumbs-down-alt:before{content:"\f088"}
.icon-star-half:before{content:"\f089"}
.icon-heart-empty:before{content:"\f08a"}
.icon-signout:before{content:"\f08b"}
.icon-linkedin-sign:before{content:"\f08c"}
.icon-pushpin:before{content:"\f08d"}
.icon-external-link:before{content:"\f08e"}
.icon-signin:before{content:"\f090"}
.icon-trophy:before{content:"\f091"}
.icon-github-sign:before{content:"\f092"}
.icon-upload-alt:before{content:"\f093"}
.icon-lemon:before{content:"\f094"}
.icon-phone:before{content:"\f095"}
.icon-unchecked:before,.icon-check-empty:before{content:"\f096"}
.icon-bookmark-empty:before{content:"\f097"}
.icon-phone-sign:before{content:"\f098"}
.icon-twitter:before{content:"\f099"}
.icon-facebook:before{content:"\f09a"}
.icon-github:before{content:"\f09b"}
.icon-unlock:before{content:"\f09c"}
.icon-credit-card:before{content:"\f09d"}
.icon-rss:before{content:"\f09e"}
.icon-hdd:before{content:"\f0a0"}
.icon-bullhorn:before{content:"\f0a1"}
.icon-bell:before{content:"\f0a2"}
.icon-certificate:before{content:"\f0a3"}
.icon-hand-right:before{content:"\f0a4"}
.icon-hand-left:before{content:"\f0a5"}
.icon-hand-up:before{content:"\f0a6"}
.icon-hand-down:before{content:"\f0a7"}
.icon-circle-arrow-left:before{content:"\f0a8"}
.icon-circle-arrow-right:before{content:"\f0a9"}
.icon-circle-arrow-up:before{content:"\f0aa"}
.icon-circle-arrow-down:before{content:"\f0ab"}
.icon-globe:before{content:"\f0ac"}
.icon-wrench:before{content:"\f0ad"}
.icon-tasks:before{content:"\f0ae"}
.icon-filter:before{content:"\f0b0"}
.icon-briefcase:before{content:"\f0b1"}
.icon-fullscreen:before{content:"\f0b2"}
.icon-group:before{content:"\f0c0"}
.icon-link:before{content:"\f0c1"}
.icon-cloud:before{content:"\f0c2"}
.icon-beaker:before{content:"\f0c3"}
.icon-cut:before{content:"\f0c4"}
.icon-copy:before{content:"\f0c5"}
.icon-paperclip:before,.icon-paper-clip:before{content:"\f0c6"}
.icon-save:before{content:"\f0c7"}
.icon-sign-blank:before{content:"\f0c8"}
.icon-reorder:before{content:"\f0c9"}
.icon-list-ul:before{content:"\f0ca"}
.icon-list-ol:before{content:"\f0cb"}
.icon-strikethrough:before{content:"\f0cc"}
.icon-underline:before{content:"\f0cd"}
.icon-table:before{content:"\f0ce"}
.icon-magic:before{content:"\f0d0"}
.icon-truck:before{content:"\f0d1"}
.icon-pinterest:before{content:"\f0d2"}
.icon-pinterest-sign:before{content:"\f0d3"}
.icon-google-plus-sign:before{content:"\f0d4"}
.icon-google-plus:before{content:"\f0d5"}
.icon-money:before{content:"\f0d6"}
.icon-caret-down:before{content:"\f0d7"}
.icon-caret-up:before{content:"\f0d8"}
.icon-caret-left:before{content:"\f0d9"}
.icon-caret-right:before{content:"\f0da"}
.icon-columns:before{content:"\f0db"}
.icon-sort:before{content:"\f0dc"}
.icon-sort-down:before{content:"\f0dd"}
.icon-sort-up:before{content:"\f0de"}
.icon-envelope:before{content:"\f0e0"}
.icon-linkedin:before{content:"\f0e1"}
.icon-rotate-left:before,.icon-undo:before{content:"\f0e2"}
.icon-legal:before{content:"\f0e3"}
.icon-dashboard:before{content:"\f0e4"}
.icon-comment-alt:before{content:"\f0e5"}
.icon-comments-alt:before{content:"\f0e6"}
.icon-bolt:before{content:"\f0e7"}
.icon-sitemap:before{content:"\f0e8"}
.icon-umbrella:before{content:"\f0e9"}
.icon-paste:before{content:"\f0ea"}
.icon-lightbulb:before{content:"\f0eb"}
.icon-exchange:before{content:"\f0ec"}
.icon-cloud-download:before{content:"\f0ed"}
.icon-cloud-upload:before{content:"\f0ee"}
.icon-user-md:before{content:"\f0f0"}
.icon-stethoscope:before{content:"\f0f1"}
.icon-suitcase:before{content:"\f0f2"}
.icon-bell-alt:before{content:"\f0f3"}
.icon-coffee:before{content:"\f0f4"}
.icon-food:before{content:"\f0f5"}
.icon-file-text-alt:before{content:"\f0f6"}
.icon-building:before{content:"\f0f7"}
.icon-hospital:before{content:"\f0f8"}
.icon-ambulance:before{content:"\f0f9"}
.icon-medkit:before{content:"\f0fa"}
.icon-fighter-jet:before{content:"\f0fb"}
.icon-beer:before{content:"\f0fc"}
.icon-h-sign:before{content:"\f0fd"}
.icon-plus-sign-alt:before{content:"\f0fe"}
.icon-double-angle-left:before{content:"\f100"}
.icon-double-angle-right:before{content:"\f101"}
.icon-double-angle-up:before{content:"\f102"}
.icon-double-angle-down:before{content:"\f103"}
.icon-angle-left:before{content:"\f104"}
.icon-angle-right:before{content:"\f105"}
.icon-angle-up:before{content:"\f106"}
.icon-angle-down:before{content:"\f107"}
.icon-desktop:before{content:"\f108"}
.icon-laptop:before{content:"\f109"}
.icon-tablet:before{content:"\f10a"}
.icon-mobile-phone:before{content:"\f10b"}
.icon-circle-blank:before{content:"\f10c"}
.icon-quote-left:before{content:"\f10d"}
.icon-quote-right:before{content:"\f10e"}
.icon-spinner:before{content:"\f110"}
.icon-circle:before{content:"\f111"}
.icon-mail-reply:before,.icon-reply:before{content:"\f112"}
.icon-github-alt:before{content:"\f113"}
.icon-folder-close-alt:before{content:"\f114"}
.icon-folder-open-alt:before{content:"\f115"}
.icon-expand-alt:before{content:"\f116"}
.icon-collapse-alt:before{content:"\f117"}
.icon-smile:before{content:"\f118"}
.icon-frown:before{content:"\f119"}
.icon-meh:before{content:"\f11a"}
.icon-gamepad:before{content:"\f11b"}
.icon-keyboard:before{content:"\f11c"}
.icon-flag-alt:before{content:"\f11d"}
.icon-flag-checkered:before{content:"\f11e"}
.icon-terminal:before{content:"\f120"}
.icon-code:before{content:"\f121"}
.icon-reply-all:before{content:"\f122"}
.icon-mail-reply-all:before{content:"\f122"}
.icon-star-half-full:before,.icon-star-half-empty:before{content:"\f123"}
.icon-location-arrow:before{content:"\f124"}
.icon-crop:before{content:"\f125"}
.icon-code-fork:before{content:"\f126"}
.icon-unlink:before{content:"\f127"}
.icon-question:before{content:"\f128"}
.icon-info:before{content:"\f129"}
.icon-exclamation:before{content:"\f12a"}
.icon-superscript:before{content:"\f12b"}
.icon-subscript:before{content:"\f12c"}
.icon-eraser:before{content:"\f12d"}
.icon-puzzle-piece:before{content:"\f12e"}
.icon-microphone:before{content:"\f130"}
.icon-microphone-off:before{content:"\f131"}
.icon-shield:before{content:"\f132"}
.icon-calendar-empty:before{content:"\f133"}
.icon-fire-extinguisher:before{content:"\f134"}
.icon-rocket:before{content:"\f135"}
.icon-maxcdn:before{content:"\f136"}
.icon-chevron-sign-left:before{content:"\f137"}
.icon-chevron-sign-right:before{content:"\f138"}
.icon-chevron-sign-up:before{content:"\f139"}
.icon-chevron-sign-down:before{content:"\f13a"}
.icon-html5:before{content:"\f13b"}
.icon-css3:before{content:"\f13c"}
.icon-anchor:before{content:"\f13d"}
.icon-unlock-alt:before{content:"\f13e"}
.icon-bullseye:before{content:"\f140"}
.icon-ellipsis-horizontal:before{content:"\f141"}
.icon-ellipsis-vertical:before{content:"\f142"}
.icon-rss-sign:before{content:"\f143"}
.icon-play-sign:before{content:"\f144"}
.icon-ticket:before{content:"\f145"}
.icon-minus-sign-alt:before{content:"\f146"}
.icon-check-minus:before{content:"\f147"}
.icon-level-up:before{content:"\f148"}
.icon-level-down:before{content:"\f149"}
.icon-check-sign:before{content:"\f14a"}
.icon-edit-sign:before{content:"\f14b"}
.icon-external-link-sign:before{content:"\f14c"}
.icon-share-sign:before{content:"\f14d"}
.icon-compass:before{content:"\f14e"}
.icon-collapse:before{content:"\f150"}
.icon-collapse-top:before{content:"\f151"}
.icon-expand:before{content:"\f152"}
.icon-euro:before,.icon-eur:before{content:"\f153"}
.icon-gbp:before{content:"\f154"}
.icon-dollar:before,.icon-usd:before{content:"\f155"}
.icon-rupee:before,.icon-inr:before{content:"\f156"}
.icon-yen:before,.icon-jpy:before{content:"\f157"}
.icon-renminbi:before,.icon-cny:before{content:"\f158"}
.icon-won:before,.icon-krw:before{content:"\f159"}
.icon-bitcoin:before,.icon-btc:before{content:"\f15a"}
.icon-file:before{content:"\f15b"}
.icon-file-text:before{content:"\f15c"}
.icon-sort-by-alphabet:before{content:"\f15d"}
.icon-sort-by-alphabet-alt:before{content:"\f15e"}
.icon-sort-by-attributes:before{content:"\f160"}
.icon-sort-by-attributes-alt:before{content:"\f161"}
.icon-sort-by-order:before{content:"\f162"}
.icon-sort-by-order-alt:before{content:"\f163"}
.icon-thumbs-up:before{content:"\f164"}
.icon-thumbs-down:before{content:"\f165"}
.icon-youtube-sign:before{content:"\f166"}
.icon-youtube:before{content:"\f167"}
.icon-xing:before{content:"\f168"}
.icon-xing-sign:before{content:"\f169"}
.icon-youtube-play:before{content:"\f16a"}
.icon-dropbox:before{content:"\f16b"}
.icon-stackexchange:before{content:"\f16c"}
.icon-instagram:before{content:"\f16d"}
.icon-flickr:before{content:"\f16e"}
.icon-adn:before{content:"\f170"}
.icon-bitbucket:before{content:"\f171"}
.icon-bitbucket-sign:before{content:"\f172"}
.icon-tumblr:before{content:"\f173"}
.icon-tumblr-sign:before{content:"\f174"}
.icon-long-arrow-down:before{content:"\f175"}
.icon-long-arrow-up:before{content:"\f176"}
.icon-long-arrow-left:before{content:"\f177"}
.icon-long-arrow-right:before{content:"\f178"}
.icon-apple:before{content:"\f179"}
.icon-windows:before{content:"\f17a"}
.icon-android:before{content:"\f17b"}
.icon-linux:before{content:"\f17c"}
.icon-dribbble:before{content:"\f17d"}
.icon-skype:before{content:"\f17e"}
.icon-foursquare:before{content:"\f180"}
.icon-trello:before{content:"\f181"}
.icon-female:before{content:"\f182"}
.icon-male:before{content:"\f183"}
.icon-gittip:before{content:"\f184"}
.icon-sun:before{content:"\f185"}
.icon-moon:before{content:"\f186"}
.icon-archive:before{content:"\f187"}
.icon-bug:before{content:"\f188"}
.icon-vk:before{content:"\f189"}
.icon-weibo:before{content:"\f18a"}
.icon-renren:before{content:"\f18b"}
code{color:#000}
pre{font-size:inherit;line-height:inherit}
.border-box-sizing{box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box}
.corner-all{border-radius:4px}
.hbox{display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}
.hbox>*{-webkit-box-flex:0;-moz-box-flex:0;box-flex:0;flex:none}
.vbox{display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}
.vbox>*{-webkit-box-flex:0;-moz-box-flex:0;box-flex:0;flex:none}
.hbox.reverse,.vbox.reverse,.reverse{-webkit-box-direction:reverse;-moz-box-direction:reverse;box-direction:reverse;flex-direction:row-reverse}
.hbox.box-flex0,.vbox.box-flex0,.box-flex0{-webkit-box-flex:0;-moz-box-flex:0;box-flex:0;flex:none;width:auto}
.hbox.box-flex1,.vbox.box-flex1,.box-flex1{-webkit-box-flex:1;-moz-box-flex:1;box-flex:1;flex:1}
.hbox.box-flex,.vbox.box-flex,.box-flex{-webkit-box-flex:1;-moz-box-flex:1;box-flex:1;flex:1}
.hbox.box-flex2,.vbox.box-flex2,.box-flex2{-webkit-box-flex:2;-moz-box-flex:2;box-flex:2;flex:2}
.box-group1{-webkit-box-flex-group:1;-moz-box-flex-group:1;box-flex-group:1}
.box-group2{-webkit-box-flex-group:2;-moz-box-flex-group:2;box-flex-group:2}
.hbox.start,.vbox.start,.start{-webkit-box-pack:start;-moz-box-pack:start;box-pack:start;justify-content:flex-start}
.hbox.end,.vbox.end,.end{-webkit-box-pack:end;-moz-box-pack:end;box-pack:end;justify-content:flex-end}
.hbox.center,.vbox.center,.center{-webkit-box-pack:center;-moz-box-pack:center;box-pack:center;justify-content:center}
.hbox.align-start,.vbox.align-start,.align-start{-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start}
.hbox.align-end,.vbox.align-end,.align-end{-webkit-box-align:end;-moz-box-align:end;box-align:end;align-items:flex-end}
.hbox.align-center,.vbox.align-center,.align-center{-webkit-box-align:center;-moz-box-align:center;box-align:center;align-items:center}
div.error{margin:2em;text-align:center}
div.error>h1{font-size:500%;line-height:normal}
div.error>p{font-size:200%;line-height:normal}
div.traceback-wrapper{text-align:left;max-width:800px;margin:auto}
body{background-color:#fff;position:absolute;left:0;right:0;top:0;bottom:0;overflow:visible}
div#header{display:none}
#ipython_notebook{padding-left:16px}
#noscript{width:auto;padding-top:16px;padding-bottom:16px;text-align:center;font-size:22px;color:#f00;font-weight:bold}
#ipython_notebook img{font-family:Verdana,"Helvetica Neue",Arial,Helvetica,Geneva,sans-serif;height:24px;text-decoration:none;color:#000}
#site{width:100%;display:none}
.ui-button .ui-button-text{padding:.2em .8em;font-size:77%}
input.ui-button{padding:.3em .9em}
.navbar span{margin-top:3px}
span#login_widget{float:right}
.nav-header{text-transform:none}
.navbar-nobg{background-color:transparent;background-image:none}
#header>span{margin-top:10px}
.modal_stretch{display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch;height:80%}.modal_stretch .modal-body{max-height:none;flex:1}
@media (min-width:768px){.modal{width:700px;margin-left:-350px}}.center-nav{display:inline-block;margin-bottom:-4px}
.alternate_upload{background-color:none;display:inline}
.alternate_upload.form{padding:0;margin:0}
.alternate_upload input.fileinput{background-color:#f00;position:relative;opacity:0;z-index:2;width:295px;margin-left:163px;cursor:pointer;height:26px}
ul#tabs{margin-bottom:4px}
ul#tabs a{padding-top:4px;padding-bottom:4px}
ul.breadcrumb a:focus,ul.breadcrumb a:hover{text-decoration:none}
ul.breadcrumb i.icon-home{font-size:16px;margin-right:4px}
ul.breadcrumb span{color:#5e5e5e}
.list_toolbar{padding:4px 0 4px 0}
.list_toolbar [class*="span"]{min-height:26px}
.list_header{font-weight:bold}
.list_container{margin-top:4px;margin-bottom:20px;border:1px solid #ababab;border-radius:4px}
.list_container>div{border-bottom:1px solid #ababab}.list_container>div:hover .list-item{background-color:#f00}
.list_container>div:last-child{border:none}
.list_item:hover .list_item{background-color:#ddd}
.list_item a{text-decoration:none}
.list_header>div,.list_item>div{padding-top:4px;padding-bottom:4px;padding-left:7px;padding-right:7px;height:22px;line-height:22px}
.item_name{line-height:22px;height:26px}
.item_icon{font-size:14px;color:#5e5e5e;margin-right:7px}
.item_buttons{line-height:1em}
.toolbar_info{height:26px;line-height:26px}
input.nbname_input,input.engine_num_input{padding-top:3px;padding-bottom:3px;height:14px;line-height:14px;margin:0}
input.engine_num_input{width:60px}
.highlight_text{color:#00f}
#project_name>.breadcrumb{padding:0;margin-bottom:0;background-color:transparent;font-weight:bold}
.folder_icon:before{font-family:FontAwesome;font-weight:normal;font-style:normal;text-decoration:inherit;-webkit-font-smoothing:antialiased;*margin-right:.3em;content:"\f114"}
.notebook_icon:before{font-family:FontAwesome;font-weight:normal;font-style:normal;text-decoration:inherit;-webkit-font-smoothing:antialiased;*margin-right:.3em;content:"\f02d"}
.ansibold{font-weight:bold}
.ansiblack{color:#000}
.ansired{color:#8b0000}
.ansigreen{color:#006400}
.ansiyellow{color:#a52a2a}
.ansiblue{color:#00008b}
.ansipurple{color:#9400d3}
.ansicyan{color:#4682b4}
.ansigray{color:#808080}
.ansibgblack{background-color:#000}
.ansibgred{background-color:#f00}
.ansibggreen{background-color:#008000}
.ansibgyellow{background-color:#ff0}
.ansibgblue{background-color:#00f}
.ansibgpurple{background-color:#f0f}
.ansibgcyan{background-color:#0ff}
.ansibggray{background-color:#808080}
div.cell{border:1px solid transparent;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}div.cell.selected{border-radius:4px;border:thin #ababab solid}
div.cell.edit_mode{border-radius:4px;border:thin #008000 solid}
div.cell{width:100%;padding:5px 5px 5px 0;margin:0;outline:none}
div.prompt{min-width:11ex;padding:.4em;margin:0;font-family:monospace;text-align:right;line-height:1.21429em}
@media (max-width:480px){div.prompt{text-align:left}}div.inner_cell{display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch;-webkit-box-flex:1;-moz-box-flex:1;box-flex:1;flex:1}
div.input_area{border:1px solid #cfcfcf;border-radius:4px;background:#f7f7f7;line-height:1.21429em}
div.prompt:empty{padding-top:0;padding-bottom:0}
div.input{page-break-inside:avoid;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}
@media (max-width:480px){div.input{display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}}div.input_prompt{color:#000080;border-top:1px solid transparent}
div.input_area>div.highlight{margin:.4em;border:none;padding:0;background-color:transparent}
div.input_area>div.highlight>pre{margin:0;border:none;padding:0;background-color:transparent}
.CodeMirror{line-height:1.21429em;height:auto;background:none;}
.CodeMirror-scroll{overflow-y:hidden;overflow-x:auto}
.CodeMirror-lines{padding:.4em}
.CodeMirror-linenumber{padding:0 8px 0 4px}
.CodeMirror-gutters{border-bottom-left-radius:4px;border-top-left-radius:4px}
.CodeMirror pre{padding:0;border:0;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
pre code{display:block;padding:.5em}
.highlight-base,pre code,pre .subst,pre .tag .title,pre .lisp .title,pre .clojure .built_in,pre .nginx .title{color:#000}
.highlight-string,pre .string,pre .constant,pre .parent,pre .tag .value,pre .rules .value,pre .rules .value .number,pre .preprocessor,pre .ruby .symbol,pre .ruby .symbol .string,pre .aggregate,pre .template_tag,pre .django .variable,pre .smalltalk .class,pre .addition,pre .flow,pre .stream,pre .bash .variable,pre .apache .tag,pre .apache .cbracket,pre .tex .command,pre .tex .special,pre .erlang_repl .function_or_atom,pre .markdown .header{color:#ba2121}
.highlight-comment,pre .comment,pre .annotation,pre .template_comment,pre .diff .header,pre .chunk,pre .markdown .blockquote{color:#408080;font-style:italic}
.highlight-number,pre .number,pre .date,pre .regexp,pre .literal,pre .smalltalk .symbol,pre .smalltalk .char,pre .go .constant,pre .change,pre .markdown .bullet,pre .markdown .link_url{color:#080}
pre .label,pre .javadoc,pre .ruby .string,pre .decorator,pre .filter .argument,pre .localvars,pre .array,pre .attr_selector,pre .important,pre .pseudo,pre .pi,pre .doctype,pre .deletion,pre .envvar,pre .shebang,pre .apache .sqbracket,pre .nginx .built_in,pre .tex .formula,pre .erlang_repl .reserved,pre .prompt,pre .markdown .link_label,pre .vhdl .attribute,pre .clojure .attribute,pre .coffeescript .property{color:#88f}
.highlight-keyword,pre .keyword,pre .id,pre .phpdoc,pre .aggregate,pre .css .tag,pre .javadoctag,pre .phpdoc,pre .yardoctag,pre .smalltalk .class,pre .winutils,pre .bash .variable,pre .apache .tag,pre .go .typename,pre .tex .command,pre .markdown .strong,pre .request,pre .status{color:#008000;font-weight:bold}
.highlight-builtin,pre .built_in{color:#008000}
pre .markdown .emphasis{font-style:italic}
pre .nginx .built_in{font-weight:normal}
pre .coffeescript .javascript,pre .javascript .xml,pre .tex .formula,pre .xml .javascript,pre .xml .vbscript,pre .xml .css,pre .xml .cdata{opacity:.5}
.cm-s-ipython span.cm-variable{color:#000}
.cm-s-ipython span.cm-keyword{color:#008000;font-weight:bold}
.cm-s-ipython span.cm-number{color:#080}
.cm-s-ipython span.cm-comment{color:#408080;font-style:italic}
.cm-s-ipython span.cm-string{color:#ba2121}
.cm-s-ipython span.cm-builtin{color:#008000}
.cm-s-ipython span.cm-error{color:#f00}
.cm-s-ipython span.cm-operator{color:#a2f;font-weight:bold}
.cm-s-ipython span.cm-meta{color:#a2f}
.cm-s-ipython span.cm-tab{background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);background-position:right;background-repeat:no-repeat}
div.output_wrapper{position:relative;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}
div.output_scroll{height:24em;width:100%;overflow:auto;border-radius:4px;-webkit-box-shadow:inset 0 2px 8px rgba(0,0,0,0.8);-moz-box-shadow:inset 0 2px 8px rgba(0,0,0,0.8);box-shadow:inset 0 2px 8px rgba(0,0,0,0.8);display:block}
div.output_collapsed{margin:0;padding:0;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}
div.out_prompt_overlay{height:100%;padding:0 .4em;position:absolute;border-radius:4px}
div.out_prompt_overlay:hover{-webkit-box-shadow:inset 0 0 1px #000;-moz-box-shadow:inset 0 0 1px #000;box-shadow:inset 0 0 1px #000;background:rgba(240,240,240,0.5)}
div.output_prompt{color:#8b0000}
div.output_area{padding:0;page-break-inside:avoid;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}div.output_area .MathJax_Display{text-align:left !important}
div.output_area .rendered_html table{margin-left:0;margin-right:0}
div.output_area .rendered_html img{margin-left:0;margin-right:0}
.output{display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}
@media (max-width:480px){div.output_area{display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}}div.output_area pre{margin:0;padding:0;border:0;vertical-align:baseline;color:#000;background-color:transparent;border-radius:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0}
div.output_subarea{padding:.4em .4em 0 .4em;-webkit-box-flex:1;-moz-box-flex:1;box-flex:1;flex:1}
div.output_text{text-align:left;color:#000;line-height:1.21429em}
div.output_stderr{background:#fdd;}
div.output_latex{text-align:left}
div.output_javascript:empty{padding:0}
.js-error{color:#8b0000}
div.raw_input_container{font-family:monospace;padding-top:5px}
span.raw_input_prompt{}
input.raw_input{font-family:inherit;font-size:inherit;color:inherit;width:auto;vertical-align:baseline;padding:0 .25em;margin:0 .25em}
input.raw_input:focus{box-shadow:none}
p.p-space{margin-bottom:10px}
.rendered_html{color:#000;}.rendered_html em{font-style:italic}
.rendered_html strong{font-weight:bold}
.rendered_html u{text-decoration:underline}
.rendered_html :link{text-decoration:underline}
.rendered_html :visited{text-decoration:underline}
.rendered_html h1{font-size:185.7%;margin:1.08em 0 0 0;font-weight:bold;line-height:1}
.rendered_html h2{font-size:157.1%;margin:1.27em 0 0 0;font-weight:bold;line-height:1}
.rendered_html h3{font-size:128.6%;margin:1.55em 0 0 0;font-weight:bold;line-height:1}
.rendered_html h4{font-size:100%;margin:2em 0 0 0;font-weight:bold;line-height:1}
.rendered_html h5{font-size:100%;margin:2em 0 0 0;font-weight:bold;line-height:1;font-style:italic}
.rendered_html h6{font-size:100%;margin:2em 0 0 0;font-weight:bold;line-height:1;font-style:italic}
.rendered_html h1:first-child{margin-top:.538em}
.rendered_html h2:first-child{margin-top:.636em}
.rendered_html h3:first-child{margin-top:.777em}
.rendered_html h4:first-child{margin-top:1em}
.rendered_html h5:first-child{margin-top:1em}
.rendered_html h6:first-child{margin-top:1em}
.rendered_html ul{list-style:disc;margin:0 2em}
.rendered_html ul ul{list-style:square;margin:0 2em}
.rendered_html ul ul ul{list-style:circle;margin:0 2em}
.rendered_html ol{list-style:decimal;margin:0 2em}
.rendered_html ol ol{list-style:upper-alpha;margin:0 2em}
.rendered_html ol ol ol{list-style:lower-alpha;margin:0 2em}
.rendered_html ol ol ol ol{list-style:lower-roman;margin:0 2em}
.rendered_html ol ol ol ol ol{list-style:decimal;margin:0 2em}
.rendered_html *+ul{margin-top:1em}
.rendered_html *+ol{margin-top:1em}
.rendered_html hr{color:#000;background-color:#000}
.rendered_html pre{margin:1em 2em}
.rendered_html pre,.rendered_html code{border:0;background-color:#fff;color:#000;font-size:100%;padding:0}
.rendered_html blockquote{margin:1em 2em}
.rendered_html table{margin-left:auto;margin-right:auto;border:1px solid #000;border-collapse:collapse}
.rendered_html tr,.rendered_html th,.rendered_html td{border:1px solid #000;border-collapse:collapse;margin:1em 2em}
.rendered_html td,.rendered_html th{text-align:left;vertical-align:middle;padding:4px}
.rendered_html th{font-weight:bold}
.rendered_html *+table{margin-top:1em}
.rendered_html p{text-align:justify}
.rendered_html *+p{margin-top:1em}
.rendered_html img{display:block;margin-left:auto;margin-right:auto}
.rendered_html *+img{margin-top:1em}
div.text_cell{padding:5px 5px 5px 0;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}
@media (max-width:480px){div.text_cell>div.prompt{display:none}}div.text_cell_render{outline:none;resize:none;width:inherit;border-style:none;padding:.5em .5em .5em .4em;color:#000}
a.anchor-link:link{text-decoration:none;padding:0 20px;visibility:hidden}
h1:hover .anchor-link,h2:hover .anchor-link,h3:hover .anchor-link,h4:hover .anchor-link,h5:hover .anchor-link,h6:hover .anchor-link{visibility:visible}
div.cell.text_cell.rendered{padding:0}
.widget-area{page-break-inside:avoid;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}.widget-area .widget-subarea{padding:.44em .4em .4em 1px;margin-left:6px;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch;-webkit-box-flex:2;-moz-box-flex:2;box-flex:2;flex:2;-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start}
.widget-hlabel{min-width:10ex;padding-right:8px;padding-top:3px;text-align:right;vertical-align:text-top}
.widget-vlabel{padding-bottom:5px;text-align:center;vertical-align:text-bottom}
.widget-hreadout{padding-left:8px;padding-top:3px;text-align:left;vertical-align:text-top}
.widget-vreadout{padding-top:5px;text-align:center;vertical-align:text-top}
.slide-track{border:1px solid #ccc;background:#fff;border-radius:4px;}
.widget-hslider{padding-left:8px;padding-right:5px;overflow:visible;width:348px;height:5px;max-height:5px;margin-top:11px;margin-bottom:10px;border:1px solid #ccc;background:#fff;border-radius:4px;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}.widget-hslider .ui-slider{border:0 !important;background:none !important;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch;-webkit-box-flex:1;-moz-box-flex:1;box-flex:1;flex:1}.widget-hslider .ui-slider .ui-slider-handle{width:14px !important;height:28px !important;margin-top:-8px !important}
.widget-vslider{padding-bottom:8px;overflow:visible;width:5px;max-width:5px;height:250px;margin-left:12px;border:1px solid #ccc;background:#fff;border-radius:4px;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}.widget-vslider .ui-slider{border:0 !important;background:none !important;margin-left:-4px;margin-top:5px;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch;-webkit-box-flex:1;-moz-box-flex:1;box-flex:1;flex:1}.widget-vslider .ui-slider .ui-slider-handle{width:28px !important;height:14px !important;margin-left:-9px}
.widget-text{width:350px;margin:0 !important}
.widget-listbox{width:364px;margin-bottom:0}
.widget-numeric-text{width:150px;margin:0 !important}
.widget-progress{width:363px}.widget-progress .bar{-webkit-transition:none;-moz-transition:none;-ms-transition:none;-o-transition:none;transition:none}
.widget-combo-btn{min-width:138px;}
.widget-box{margin:5px;-webkit-box-pack:start;-moz-box-pack:start;box-pack:start;justify-content:flex-start;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start}
.widget-hbox{margin:5px;-webkit-box-pack:start;-moz-box-pack:start;box-pack:start;justify-content:flex-start;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}
.widget-hbox-single{margin:5px;-webkit-box-pack:start;-moz-box-pack:start;box-pack:start;justify-content:flex-start;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch;height:30px}
.widget-vbox{margin:5px;-webkit-box-pack:start;-moz-box-pack:start;box-pack:start;justify-content:flex-start;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch}
.widget-vbox-single{margin:5px;-webkit-box-pack:start;-moz-box-pack:start;box-pack:start;justify-content:flex-start;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start;display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch;width:30px}
.widget-modal{overflow:hidden;position:absolute !important;top:0;left:0;margin-left:0 !important}
.widget-modal-body{max-height:none !important}
.widget-container{box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;-webkit-box-align:start;-moz-box-align:start;box-align:start;align-items:flex-start}
.widget-radio-box{display:-webkit-box;-webkit-box-orient:vertical;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:vertical;-moz-box-align:stretch;display:box;box-orient:vertical;box-align:stretch;display:flex;flex-direction:column;align-items:stretch;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box;padding-top:4px}
.docked-widget-modal{overflow:hidden;position:relative !important;top:0 !important;left:0 !important;margin-left:0 !important}
body{background-color:#fff}
body.notebook_app{overflow:hidden}
@media (max-width:767px){body.notebook_app{padding-left:0;padding-right:0}}span#notebook_name{height:1em;line-height:1em;padding:3px;border:none;font-size:146.5%}
div#notebook_panel{margin:0 0 0 0;padding:0;-webkit-box-shadow:0 -1px 10px rgba(0,0,0,0.1);-moz-box-shadow:0 -1px 10px rgba(0,0,0,0.1);box-shadow:0 -1px 10px rgba(0,0,0,0.1)}
div#notebook{font-size:14px;line-height:20px;overflow-y:scroll;overflow-x:auto;width:100%;padding:1em 0 1em 0;margin:0;border-top:1px solid #ababab;outline:none;box-sizing:border-box;-moz-box-sizing:border-box;-webkit-box-sizing:border-box}
div.ui-widget-content{border:1px solid #ababab;outline:none}
pre.dialog{background-color:#f7f7f7;border:1px solid #ddd;border-radius:4px;padding:.4em;padding-left:2em}
p.dialog{padding:.2em}
pre,code,kbd,samp{white-space:pre-wrap}
#fonttest{font-family:monospace}
p{margin-bottom:0}
.end_space{height:200px}
.celltoolbar{border:thin solid #cfcfcf;border-bottom:none;background:#eee;border-radius:3px 3px 0 0;width:100%;-webkit-box-pack:end;height:22px;display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch;-webkit-box-direction:reverse;-moz-box-direction:reverse;box-direction:reverse;flex-direction:row-reverse}
.ctb_hideshow{display:none;vertical-align:bottom;padding-right:2px}
.celltoolbar>div{padding-top:0}
.ctb_global_show .ctb_show.ctb_hideshow{display:block}
.ctb_global_show .ctb_show+.input_area,.ctb_global_show .ctb_show+div.text_cell_input{border-top-right-radius:0;border-top-left-radius:0}
.celltoolbar .button_container select{margin:10px;margin-top:1px;margin-bottom:0;padding:0;font-size:87%;width:auto;display:inline-block;height:18px;line-height:18px;vertical-align:top}
.celltoolbar label{display:inline-block;height:15px;line-height:15px;vertical-align:top}
.celltoolbar label span{font-size:85%}
.celltoolbar input[type=checkbox]{margin:0;margin-left:4px;margin-right:4px}
.celltoolbar .ui-button{border:none;vertical-align:top;height:20px;min-width:30px}
.completions{position:absolute;z-index:10;overflow:hidden;border:1px solid #ababab;border-radius:4px;-webkit-box-shadow:0 6px 10px -1px #adadad;-moz-box-shadow:0 6px 10px -1px #adadad;box-shadow:0 6px 10px -1px #adadad}
.completions select{background:#fff;outline:none;border:none;padding:0;margin:0;overflow:auto;font-family:monospace;font-size:110%;color:#000;width:auto}
.completions select option.context{color:#0064cd}
#menubar .navbar-inner{min-height:28px;border-top:1px;border-radius:0 0 4px 4px}
#menubar .navbar{margin-bottom:8px}
.nav-wrapper{border-bottom:1px solid #d4d4d4}
#menubar li.dropdown{line-height:12px}
i.menu-icon{padding-top:4px}
ul#help_menu li a{overflow:hidden;padding-right:2.2em}ul#help_menu li a i{margin-right:-1.2em}
#notification_area{z-index:10}
.indicator_area{color:#777;padding:4px 3px;margin:0;width:11px;z-index:10;text-align:center}
#kernel_indicator{margin-right:-16px}
.edit_mode_icon:before{font-family:FontAwesome;font-weight:normal;font-style:normal;text-decoration:inherit;-webkit-font-smoothing:antialiased;*margin-right:.3em;content:"\f040"}
.command_mode_icon:before{font-family:FontAwesome;font-weight:normal;font-style:normal;text-decoration:inherit;-webkit-font-smoothing:antialiased;*margin-right:.3em;content:' '}
.kernel_idle_icon:before{font-family:FontAwesome;font-weight:normal;font-style:normal;text-decoration:inherit;-webkit-font-smoothing:antialiased;*margin-right:.3em;content:"\f10c"}
.kernel_busy_icon:before{font-family:FontAwesome;font-weight:normal;font-style:normal;text-decoration:inherit;-webkit-font-smoothing:antialiased;*margin-right:.3em;content:"\f111"}
.notification_widget{color:#777;padding:1px 12px;margin:2px 4px;z-index:10;border:1px solid #ccc;border-radius:4px;background:rgba(240,240,240,0.5)}.notification_widget.span{padding-right:2px}
div#pager_splitter{height:8px}
#pager-container{position:relative;padding:15px 0}
div#pager{font-size:14px;line-height:20px;overflow:auto;display:none}div#pager pre{line-height:1.21429em;color:#000;background-color:#f7f7f7;padding:.4em}
.quickhelp{display:-webkit-box;-webkit-box-orient:horizontal;-webkit-box-align:stretch;display:-moz-box;-moz-box-orient:horizontal;-moz-box-align:stretch;display:box;box-orient:horizontal;box-align:stretch;display:flex;flex-direction:row;align-items:stretch}
.shortcut_key{display:inline-block;width:20ex;text-align:right;font-family:monospace}
.shortcut_descr{display:inline-block;-webkit-box-flex:1;-moz-box-flex:1;box-flex:1;flex:1}
span#save_widget{padding:0 5px;margin-top:12px}
span#checkpoint_status,span#autosave_status{font-size:small}
@media (max-width:767px){span#save_widget{font-size:small} span#checkpoint_status,span#autosave_status{font-size:x-small}}@media (max-width:767px){span#checkpoint_status,span#autosave_status{display:none}}@media (min-width:768px) and (max-width:979px){span#checkpoint_status{display:none} span#autosave_status{font-size:x-small}}.toolbar{padding:0 10px;margin-top:-5px}.toolbar select,.toolbar label{width:auto;height:26px;vertical-align:middle;margin-right:2px;margin-bottom:0;display:inline;font-size:92%;margin-left:.3em;margin-right:.3em;padding:0;padding-top:3px}
.toolbar .btn{padding:2px 8px}
.toolbar .btn-group{margin-top:0}
.toolbar-inner{border:none !important;-webkit-box-shadow:none !important;-moz-box-shadow:none !important;box-shadow:none !important}
#maintoolbar{margin-bottom:0}
@-moz-keyframes fadeOut{from{opacity:1} to{opacity:0}}@-webkit-keyframes fadeOut{from{opacity:1} to{opacity:0}}@-moz-keyframes fadeIn{from{opacity:0} to{opacity:1}}@-webkit-keyframes fadeIn{from{opacity:0} to{opacity:1}}.bigtooltip{overflow:auto;height:200px;-webkit-transition-property:height;-webkit-transition-duration:500ms;-moz-transition-property:height;-moz-transition-duration:500ms;transition-property:height;transition-duration:500ms}
.smalltooltip{-webkit-transition-property:height;-webkit-transition-duration:500ms;-moz-transition-property:height;-moz-transition-duration:500ms;transition-property:height;transition-duration:500ms;text-overflow:ellipsis;overflow:hidden;height:80px}
.tooltipbuttons{position:absolute;padding-right:15px;top:0;right:0}
.tooltiptext{padding-right:30px}
.ipython_tooltip{max-width:700px;-webkit-animation:fadeOut 400ms;-moz-animation:fadeOut 400ms;animation:fadeOut 400ms;-webkit-animation:fadeIn 400ms;-moz-animation:fadeIn 400ms;animation:fadeIn 400ms;vertical-align:middle;background-color:#f7f7f7;overflow:visible;border:#ababab 1px solid;outline:none;padding:3px;margin:0;padding-left:7px;font-family:monospace;min-height:50px;-moz-box-shadow:0 6px 10px -1px #adadad;-webkit-box-shadow:0 6px 10px -1px #adadad;box-shadow:0 6px 10px -1px #adadad;border-radius:4px;position:absolute;z-index:2}.ipython_tooltip a{float:right}
.ipython_tooltip .tooltiptext pre{border:0;-webkit-border-radius:0;-moz-border-radius:0;border-radius:0;font-size:100%;background-color:#f7f7f7}
.pretooltiparrow{left:0;margin:0;top:-16px;width:40px;height:16px;overflow:hidden;position:absolute}
.pretooltiparrow:before{background-color:#f7f7f7;border:1px #ababab solid;z-index:11;content:"";position:absolute;left:15px;top:10px;width:25px;height:25px;-webkit-transform:rotate(45deg);-moz-transform:rotate(45deg);-ms-transform:rotate(45deg);-o-transform:rotate(45deg)}

    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #808080 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0040D0 } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}

@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration -->

</head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Introduction">Introduction<a class="anchor-link" href="#Introduction">&#182;</a></h1>
</div>
</div>
</div>

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The goal of this short quiz is to make sure you have no trouble getting up and
running with a Python distribution on your computer.</p>
<p>In developing software for the DropBot digital microfluidics platform, we make
heavy use of certain Python libraries, including <a href="http://ipython.org/notebook.html">IPython notebook</a>,
<a href="http://www.numpy.org/"><code>numpy</code></a> and <a href="http://pandas.pydata.org/"><code>pandas</code></a>. Since pandas uses numpy under the hood, this quiz
covers pandas usage.</p>
<p>If you haven&#39;t used <code>pandas</code> before, I would highly recommend watching <a href="https://www.youtube.com/watch?v=5JnMutdy6Fw">this video</a>
for a crash course before attempting this quiz.  The video is quite good, although
I <em>would</em> recommend watching it at 1.25x speed at least, since the speaker talks
<em>very</em> slowly.</p>
<p>If you can&#39;t figure out how to answer a question, no problem. Also, don&#39;t worry if
your output doesn&#39;t match exactly. We just want to get some idea of how familiar
you are with these tools.</p>
<p>When you&#39;re done, please save the notebook and email the resulting <code>.ipynb</code> file to us.</p>
<p>Thanks a lot and good luck! :)</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">
In&nbsp;[1]:
</div>
<div class="inner_cell">
    <div class="input_area">
<div class="highlight"><pre><span class="kn">import</span> <span class="nn">pandas</span> <span class="kn">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="kn">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">datetime</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Load-Toronto-weather-data-(based-on-Environment-Canada-data)">Load Toronto weather data (based on Environment Canada data)<a class="anchor-link" href="#Load-Toronto-weather-data-(based-on-Environment-Canada-data)">&#182;</a></h1>
</div>
</div>
</div>

<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">
In&nbsp;[2]:
</div>
<div class="inner_cell">
    <div class="input_area">
<div class="highlight"><pre><span class="c"># Load data from CSV file using Pandas.  Rows are indexed by date.</span>
<span class="n">df_weather</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s">&#39;2015-toronto-weather.csv&#39;</span><span class="p">,</span> <span class="n">index_col</span><span class="o">=</span><span class="s">&#39;Date/Time&#39;</span><span class="p">,</span>
                         <span class="n">parse_dates</span><span class="o">=</span><span class="p">[</span><span class="s">&#39;Date/Time&#39;</span><span class="p">],</span> <span class="n">infer_datetime_format</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
<span class="c"># Display first few rows of table.</span>
<span class="n">df_weather</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">
    Out[2]:</div>

<div class="output_html rendered_html output_subarea output_pyout">
<div style="max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Month</th>
      <th>Day</th>
      <th>Max Temp (deg C)</th>
      <th>Min Temp (deg C)</th>
      <th>Mean Temp (deg C)</th>
      <th>Total Precip (mm)</th>
    </tr>
    <tr>
      <th>Date/Time</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2015-01-01</th>
      <td>1</td>
      <td>1</td>
      <td>-0.4</td>
      <td>-6.3</td>
      <td>-3.4</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2015-01-02</th>
      <td>1</td>
      <td>2</td>
      <td>0.3</td>
      <td>-4.4</td>
      <td>-2.1</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2015-01-03</th>
      <td>1</td>
      <td>3</td>
      <td>2.9</td>
      <td>-3.6</td>
      <td>-0.4</td>
      <td>6.3</td>
    </tr>
    <tr>
      <th>2015-01-04</th>
      <td>1</td>
      <td>4</td>
      <td>5.0</td>
      <td>-4.7</td>
      <td>0.2</td>
      <td>2.8</td>
    </tr>
    <tr>
      <th>2015-01-05</th>
      <td>1</td>
      <td>5</td>
      <td>-4.5</td>
      <td>-11.8</td>
      <td>-8.2</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">
In&nbsp;[3]:
</div>
<div class="inner_cell">
    <div class="input_area">
<div class="highlight"><pre><span class="c"># Draw plots as images in the notebook.</span>
<span class="o">%</span><span class="k">matplotlib</span> <span class="n">inline</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Questions">Questions<a class="anchor-link" href="#Questions">&#182;</a></h1>
</div>
</div>
</div>

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Which-days-had-more-than-3mm-of-precipitation?">Which days had more than 3mm of precipitation?<a class="anchor-link" href="#Which-days-had-more-than-3mm-of-precipitation?">&#182;</a></h2>
</div>
</div>
</div>

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><em>Hint</em>: You may find <a href="http://pandas.pydata.org/pandas-docs/stable/indexing.html#boolean-indexing">boolean indexing</a> helpful when answering this question.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">
In&nbsp;[4]:
</div>
<div class="inner_cell">
    <div class="input_area">
<div class="highlight"><pre> 
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">
    Out[4]:</div>

<div class="output_html rendered_html output_subarea output_pyout">
<div style="max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Month</th>
      <th>Day</th>
      <th>Max Temp (deg C)</th>
      <th>Min Temp (deg C)</th>
      <th>Mean Temp (deg C)</th>
      <th>Total Precip (mm)</th>
    </tr>
    <tr>
      <th>Date/Time</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2015-04-08</th>
      <td>4</td>
      <td>8</td>
      <td>3.8</td>
      <td>1.4</td>
      <td>2.6</td>
      <td>17.3</td>
    </tr>
    <tr>
      <th>2015-04-20</th>
      <td>4</td>
      <td>20</td>
      <td>12.9</td>
      <td>4.4</td>
      <td>8.7</td>
      <td>24.5</td>
    </tr>
    <tr>
      <th>2015-05-31</th>
      <td>5</td>
      <td>31</td>
      <td>12.5</td>
      <td>8.0</td>
      <td>10.3</td>
      <td>20.3</td>
    </tr>
    <tr>
      <th>2015-06-16</th>
      <td>6</td>
      <td>16</td>
      <td>27.3</td>
      <td>15.0</td>
      <td>21.2</td>
      <td>17.7</td>
    </tr>
    <tr>
      <th>2015-06-22</th>
      <td>6</td>
      <td>22</td>
      <td>23.9</td>
      <td>16.2</td>
      <td>20.1</td>
      <td>19.0</td>
    </tr>
    <tr>
      <th>2015-06-27</th>
      <td>6</td>
      <td>27</td>
      <td>20.1</td>
      <td>12.9</td>
      <td>16.5</td>
      <td>38.2</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Plot-max/min/mean-temperature-and-total-precipitation-for-May-August">Plot max/min/mean temperature and total precipitation for May-August<a class="anchor-link" href="#Plot-max/min/mean-temperature-and-total-precipitation-for-May-August">&#182;</a></h2>
</div>
</div>
</div>

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><em>Hint</em>: Again, you may find <a href="http://pandas.pydata.org/pandas-docs/stable/indexing.html#boolean-indexing">boolean indexing</a> helpful when answering this question.</p>
<p><em>Note:</em> Be careful when combining two or more boolean index queries.  See <a href="https://youtu.be/5JnMutdy6Fw?t=31m21s">this video</a> for
more information.</p>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">
In&nbsp;[5]:
</div>
<div class="inner_cell">
    <div class="input_area">
<div class="highlight"><pre> 
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAYcAAAEdCAYAAADn46tbAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAIABJREFUeJzsnXd4VGXauO+pySSZSQ8JCYGEDhJBEUQUohTFwtrFgn3t
dXe/XXUV176fn7v7W/1s62cDFF3RXRUXQRBQLBSl9xKSkALpyaRMPb8/zpwz50zLpJEI574uLnJm
TnnmzJn3eZ/yPg9oaGhoaGhoaGhoaGhoaGhoaGhoaGhoaGhoaGhoaGhoaGhoaGhoaGhoaGic8BiA
TcDnvu0U4CtgL7AcSOoluTQ0NDROOPS9LYCC+4GdgODbfghROQwDVvq2NTQ0NDROIHKAFcDZ+C2H
3UA/39+Zvm0NDQ0NjROIj4BxwFT8yqFO8b4uYFtDQ0NDowcx9rYAwIXAUcR4Q2GYfQT87qYgVqxY
EfY9DQ0NDY2wrJk+fXphbwsRjmeBUqAIqACagQWIbqRM3z5ZRHArrVixQuguVq1a1W3n6mk0WXsG
TdaeQZO1Z+iKrJEm1n0hIP0IMADIA+YAXwNzgc+AG3z73AD8u1ek09DQ0DgB0fW2AAFMBX4LzEZM
Zf0nkAscAq4E6kMdtGLFCmHatGnHSEQNDQ2N44OVK1cyffr0kHqgL8QclKzx/QOoBab3oiwaGhoa
Jyx9wa3Up1i9enVvixA1mqw9gyZrz6DJ2jP0lKx9zXLodtra2igrK0Oni86DZrPZOHjwYA9L1T1o
svYMXZFVEAQsFgv9+/fvZqk0NI4tx7VyaGtro7i4mKFDh6LXa0aSxrGhvLyc+vp6kpJ6vuJLYWFh
j1+ju9Bk7Rl6StbjesQsKyvTFIPGMScrK4uampp29/PUNOH8YT/eGvsxkEpDo2Mc16OmTqfTFIPG
MUen00XlxnTvLMdzuBbXrvJOX0vzjfcMmqzHuXLQ0OjLCE63+If0v4ZGH0JTDhoavYVvbarg7Xz1
F8033jNosmrKQaMPMHnyZLZs2RLyvdWrVzNgwIBjLJHI7373O1577bWeu4AgqP/X0OhDaMqhFxk0
aBAxMTFBwctx48ah1+spKSnptmt9++23WK1WrFYrCQkJ6PV6edtms3H48OFuu1ZH+Pzzz0lMTOTk
k08+5tcWBIEXX3yRMWPGkJCQwIABA7jyyivZvn07ICqHZ599FpfL1TMCSBZDFywHzTfeM2iyasqh
V9HpdOTn57No0SL5tW3bttHa2hr1uoxoOeuss2hqaqKpqYkdO3YA0NDQQFNTE42NjeTk5HTr9aLl
tddeY+7cub1y7fvvv58XX3yRl156ibq6Ovbu3cvFF1/MF198AUBmZiYjRozgs88+6xkBJIvB6+2Z
82todAFNOfQy1113HfPnz5e33333Xa6//noEhavhiy++YNy4cSQmJpKbm8sTTzwhv/fhhx+Sn59P
U1MTAEuXLm03lVIIcGM0NDRwyy230L9/f3Jycnjsscfw+gasd955h8mTJ/Ob3/yG5ORkhgwZwvff
f8/bb79Nbm4u/fr1U8l/4403cscddzBz5kxsNhuFhYVhLSCn08mqVauYOnWq/Fprays33ngjKSkp
jB49mg0bNqiOKS8v57LLLiMjI4P8/Hxeeukl1bE33HADKSkpjBo1iueffz6sS2rfvn288sorfPDB
BxQWFmIymbBYLFxzzTX84Q9/kPcrLCyUlUW3I3TdctB84z2DJutxvgiuPVbsbeCovXsyRTISjEwf
ltjh404//XQWLFjA7t27GTp0KB9++CHfffcdjz76qLxPQkICCxcuZPTo0Wzbto0ZM2YwduxYfvWr
X3HVVVfx+eefc9999/HCCy9w66238uabb5Kamhq1DDfeeCOZmZkcOHAAu93OhRdeyIABA7jtttsA
WL9+Pbfddhu1tbXMmzePK6+8kksuuYQDBw6wevVqLrvsMi6//HLi4uIAeP/99/nPf/7DhAkT+P3v
f8+1117Lt99+G3Tdffv2odfrVauJn3jiCYqKijh48CB2u53zzjtPtqK8Xi8XXXQRl1xyCR9++CGl
paVMnz6d4cOHM3PmTJ544glKSkooKirCbrcza9assBbYypUrGTBgAOPHj494b0aMGMHHH38c9b3s
ED6l0JWAtIZGT3FCWw5H7W5K653d8q8rSmbu3LnMnz+fr776ilGjRpGdna16f+rUqYwePRqAMWPG
MGfOHNasWSO///LLL/P1119z9tlnM3v2bM4///yor33kyBGWLl3K3/72NywWC+np6TzwwAN88MEH
8j55eXnccMMN6HQ6rrzySsrLy5k3bx4mk4kZM2ZgNpvZv3+/vP+FF17ImWeeidls5plnnuGHH36g
rKws6Nr19fVYrVbVax999BF//OMfSUpKIicnh/vvv1+2dDZs2EB1dTWPPvooRqORvLw8br31VlnW
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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Which-months-had-a-mean-monthly-temperature-between-15-and-20-degrees?">Which months had a mean monthly temperature between 15 and 20 degrees?<a class="anchor-link" href="#Which-months-had-a-mean-monthly-temperature-between-15-and-20-degrees?">&#182;</a></h2>
</div>
</div>
</div>

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Hint: First find mean monthly temperature.  This can be done, for example, using
<a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.groupby.html"><code>groupby</code></a> (more info <a href="http://pandas.pydata.org/pandas-docs/stable/groupby.html">here</a>).  Since the weather table is indexed by date,
this can also be accomplished using <a href="http://pandas.pydata.org/pandas-docs/stable/timeseries.html#time-series-date-functionality"><code>resample</code></a>.</p>
<p>Feel free to use any method you would like.  The solutions below show the output for using
<code>groupby</code> and <code>resample</code> just for reference (you don&#39;t need to do both).</p>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Using-groupby">Using <code>groupby</code><a class="anchor-link" href="#Using-groupby">&#182;</a></h3>
</div>
</div>
</div>

<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">
In&nbsp;[6]:
</div>
<div class="inner_cell">
    <div class="input_area">
<div class="highlight"><pre> 
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">
    Out[6]:</div>

<div class="output_html rendered_html output_subarea output_pyout">
<div style="max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Day</th>
      <th>Max Temp (deg C)</th>
      <th>Min Temp (deg C)</th>
      <th>Mean Temp (deg C)</th>
      <th>Total Precip (mm)</th>
    </tr>
    <tr>
      <th>Month</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>16.0</td>
      <td>20.482143</td>
      <td>13.067857</td>
      <td>16.807143</td>
      <td>4.864286</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9.5</td>
      <td>24.316667</td>
      <td>15.594444</td>
      <td>19.977778</td>
      <td>1.994444</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Using-resample">Using <code>resample</code><a class="anchor-link" href="#Using-resample">&#182;</a></h3>
</div>
</div>
</div>

<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">
In&nbsp;[7]:
</div>
<div class="inner_cell">
    <div class="input_area">
<div class="highlight"><pre> 
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">
    Out[7]:</div>

<div class="output_html rendered_html output_subarea output_pyout">
<div style="max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Month</th>
      <th>Day</th>
      <th>Max Temp (deg C)</th>
      <th>Min Temp (deg C)</th>
      <th>Mean Temp (deg C)</th>
      <th>Total Precip (mm)</th>
    </tr>
    <tr>
      <th>Date/Time</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2015-06-30</th>
      <td>6</td>
      <td>16.0</td>
      <td>20.482143</td>
      <td>13.067857</td>
      <td>16.807143</td>
      <td>4.864286</td>
    </tr>
    <tr>
      <th>2015-08-31</th>
      <td>8</td>
      <td>9.5</td>
      <td>24.316667</td>
      <td>15.594444</td>
      <td>19.977778</td>
      <td>1.994444</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>
</html>
