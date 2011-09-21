var urls = $('a').map( function (elem) {
    return this.href.match(/Kontakt/);
});

console.log(urls);