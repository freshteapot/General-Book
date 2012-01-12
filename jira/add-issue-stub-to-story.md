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
