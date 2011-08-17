#How to add a new Document Type to inkscape

On Mac ( sorry guys, but it will most likely be /usr/share/inkscape/templates)

~~~
    /Applications/Inkscape.app/Contents/Resources/templates
~~~

cp A4.svg iphone_portait.svg

~~~
  1 <?xml version="1.0" encoding="UTF-8" standalone="no"?>
  2 <!-- Created with Inkscape (http://www.inkscape.org/) -->
  3 <svg
  4    xmlns="http://www.w3.org/2000/svg"
  5    xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
  6    xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
  7    xmlns:xlink="http://www.w3.org/1999/xlink"
  8    xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
  9    xmlns:cc="http://web.resource.org/cc/"
 10    xmlns:dc="http://purl.org/dc/elements/1.1/"
 11    width="640px"
 12    height="960px">
 13   <defs
 14      id="defs3" />
 15   <sodipodi:namedview
 16      inkscape:document-units="px"
 17      id="base"
 18      pagecolor="#ffffff"
 19      bordercolor="#666666"
 20      borderopacity="1.0"
 21      inkscape:pageopacity="0.0"
 22      inkscape:pageshadow="2"
 23      inkscape:zoom="0.50"
 24      inkscape:cx="350"
 25      inkscape:cy="520"
 26      inkscape:current-layer="layer1" />
 27   <metadata
 28      id="metadata4">
 29     <rdf:RDF>
 30       <cc:Work
 31          rdf:about="">
 32         <dc:format>image/svg+xml</dc:format>
 33         <dc:type
 34            rdf:resource="http://purl.org/dc/dcmitype/StillImage" />
 35       </cc:Work>
 36     </rdf:RDF>
 37   </metadata>
 38   <g inkscape:label="Layer 1" inkscape:groupmode="layer" id="layer1" />
 39 </svg>
~~~

I changed:



##Dimensions

Lines 11 (width) and 12 (height), note I also set the units.

##Default Units

Line 16 is where I defined it use pixels.


##Default Zoom Size

Line 23 "inkscape:zoom" I made it zoom in a little further.


##Reference

For a much more detailed view of what can be altered in this svg file. Look to the [w3c SVG for guidance](http://www.w3.org/TR/SVG/struct.html "w3c detailed Reference of SVG").


##Searched for
* size of iphone screen dimensions icon

##Links
http://www.w3.org/TR/SVG/struct.html
http://www.w3.org/Graphics/SVG/
https://bugs.launchpad.net/inkscape/+bug/176314
http://developer.apple.com/library/iOS/#documentation/UserExperience/Conceptual/MobileHIG/IconsImages/IconsImages.html

 