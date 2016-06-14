**Creating a centered fixed header or footer menu on Unbounce**

Follow the full instructions here:
https://getsatisfaction.com/unbounce/topics/creating_a_fixed_header_menu


```js
<script>

  //Fixed Menu (Header or footer) v1.3.1

  //Replace ID below with your own box ID
  var boxToAppend = '#lp-pom-box-177';

  //Set to 'header' or 'footer'
  var headerOrFooter = 'header';

  var backgroundCSS = {"position":"fixed", "left":"0", "top":"0px", "bottom":"auto", "width":"100%", "z-index":"899"};
  var colorOverlayCSS = {"position":"fixed", "left":"0", "top":"0px", "bottom":"auto", "width":"100%", "z-index":"auto", "border-style":"none none none none"};
  var childrenCSS = {"position":"fixed", "left":"auto", "top":"0px", "bottom":"auto", "width":"100%", "z-index":"999", "border-style":"none none none none", "border-width":"0px", "background":"none"};

  if (headerOrFooter === 'footer') {
    backgroundCSS["top"] = 'auto';
    backgroundCSS["bottom"] = '0px';
    colorOverlayCSS["top"] = 'auto';
    colorOverlayCSS["bottom"] = '0px';
    childrenCSS["top"] = 'auto';
    childrenCSS["bottom"] = '0px';
  }

  var boxParent = $(boxToAppend).parent();
  var boxClone = $(boxToAppend).clone()

  boxClone.appendTo(boxParent).css(backgroundCSS).children().remove();
  $(boxToAppend).css(childrenCSS);
  $(boxToAppend + '-color-overlay').appendTo(boxClone).css(colorOverlayCSS);

</script>
```
