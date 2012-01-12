#Make it so you can see the issuekey from a story overview#

This works in firefox and is ran via the console.

```
var items,size,e,e2;
items = document.getElementById("issuetable").querySelectorAll("*[data-issuekey]");
size = items.length;
for(i=0;i<size;i++){
    e=items[i];
    e2=e.querySelector(".stsummary a");
    e2.innerHTML = e2.innerHTML + "("+e.getAttribute("data-issuekey")+")";
}
```

A future upgrade will be convert it to a bookmarklet, so it just runs by a click.

##Searched for
* querySelector
* html5 read data attribute

##Links
* http://ejohn.org/blog/thoughts-on-queryselectorall/
* http://html5doctor.com/html5-custom-data-attributes/
* http://ejohn.org/blog/html-5-data-attributes/
* http://jclaes.blogspot.com/2010/11/html5-new-in-javascript-selector-api.html
* http://www.w3.org/TR/selectors-api/#nodeselector
* http://hacks.mozilla.org/2009/06/dom-selectors-api/
