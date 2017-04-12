#HSLIDE
## A Brief info to Google Maps and How to Test it
 *By the end of this we should be able to have a map that plots addresses.
*With test coverage!

#HSLIDE

<img src="pics/googleMap.png"/>

#HSLIDE
### Getting Started With Google Maps
* the first thing you need to do when doing google maps is to insert the script so that google will initialize. This is usually done in your index.js but it will be ok so long as it is inserted before the first call to google.

<img src="pics/googleMapScriptTag.png"/>
 

#HSLIDE
*To do a basic map you need a div with an id that the map can be inserted into. Normally the map code would look like this (ripped straight from google maps api tutorial)

#HSLIDE
<img src="pics/simpleMap.png"/>



#HSLIDE
* the problem with this is that when testing your javascript hasn’t been compiled and therefor google.maps.Map has not been initialize and you will get an error.

<img src="pics/googleError.png" style="height: 500px;"/>

#HSLIDE
### Enter a Service Wrapper
* In order to pass your test its best to wrap the google.maps in a service that’s only job is to serve up a brand new object. Taking in a divId and a map object.

<img src="pics/MapService.png" /> <img src="pics/MapServiceTest.png"/>

#HSLIDE
### Our Code Now Looks like this
<img src="pics/NewMapCode.png" />

#HSLIDE
### GeocodeLocations and testing Callbacks
* When you have an address coming and you want to display it on your map. You must get the co-ordinates by calling that google service. 

#HSLIDE
<img src="pics/officialMapsGeo.png" />

#HSLIDE
* See the problem?
* more calls to google.maps.Geocoder() that your tests won’t recognize.
* We can easily put the google.maps.Geocoder() into our service and test the same way as before.

#HSLIDE 
* Testing the geocode.geocode() Callback however is the most trouble

#HSLIDE
<img src="pics/FinalMapCode.png"/>

#HSLIDE Testing the callback 
* Theres two phases of testing the callback 
* Making sure the invocation method is called with the correct parameters.
* Testing what goes on inside in the callback
 
#HSLIDE
###Making sure the invocation method is called with the correct parameters.
<img src="pics/callbackTestingTop.png"/>

#HSLIDE
###Testing inside the callback
* this gets a little inception like...

<img src="pics/callbackTestingBottom.png"/>

#HSLIDE
### Final Code
<img src="pics/FinalMapCode.png" />

#HSLIDE
* for more google maps testing and life cycle testing with react check out our project https://github.allstate.com/RelationshipPlatform/allstate-rp-app-intelligence or grab one of us and we’ll be happy to pair.

#HSLIDE
###Big thanks to Andrew Kyle for showing me gitpitch :)
