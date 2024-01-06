javascript: (function() {
            var scripts = document.getElementsByTagName("script"),
                regex=/(?<=(\"|\'|\`))\/[a-zA-Z0-9_?&=\/\-\#\.]*(?=(\"|\'|\`))/g;
            const results = new Set;
            for (var i = 0; i < scripts.length; i++) {
                var t = scripts[i].src;
                "" != t && fetch(t).then(function(t) {
                    return t.text()
                }).then(function(t) {
                    var e = t.matchAll(regex);
                    for (let r of e){ 

results.add(r[0])
}
                }).catch(function(t) {
                    console.log("An error occurred: ", t)
                })
            }
            var pageContent = document.documentElement.outerHTML,
                matches = pageContent.matchAll(regex);
            for (const match of matches) results.add(match[0]);

            function writeResults() {
let domain = document.domain;
                let text = "";
                results.forEach((value) => {
                    text += `<a href="https://${domain}${value}" target="_blank">${value}</a>` + "<br>"
                });
                window.open().document.write(`<html><head><title>Endpoints Searcher | ${domain} | Made With Love By Sho3la ❤</title></head><body>` + `${text}` + "</body><style>:root {
    color-scheme: dark;
} a { color: #9da2ff; } a:link { 
  text-decoration: none; 
} 
</style></html>");
                }
                setTimeout(writeResults, 3e3);
            })();
