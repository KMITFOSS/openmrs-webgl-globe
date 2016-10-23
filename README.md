The **OpenMRS WebGL Globe** is a fork from chromeexperiments to visualize openrms implementers data provided at openmrs atlas. 

Check out the examples at http://www.chromeexperiments.com/globe, and if you create a globe, please [share it with us](http://www.chromeexperiments.com/submit). We post our favorite globes publicly.

![](http://4.bp.blogspot.com/-nB6XnTgb4AA/TcLQ4gRBtfI/AAAAAAAAH-U/vb2GuhPN6aM/globe.png)

----

**The WebGL Globe** supports data in `JSON` format, a sample of which you can find [here](https://github.com/dataarts/webgl-globe/blob/master/globe/population909500.json). `webgl-globe` makes heavy use of the [Three.js library](https://github.com/mrdoob/three.js/).

# Data Format

The following illustrates the `JSON` data format that the globe expects:

```javascript
var data = [
    [
    'seriesA', [ latitude, longitude, magnitude, latitude, longitude, magnitude, ... ]
    ],
    [
    'seriesB', [ latitude, longitude, magnitude, latitude, longitude, magnitude, ... ]
    ]
];
```

# Basic Usage

The following code polls a `JSON` file (formatted like the one above) for geo-data and adds it to an animated, interactive WebGL globe.

```javascript
// Where to put the globe?
var container = document.getElementById( 'container' );

// Make the globe
var globe = new DAT.Globe( container );

// We're going to ask a file for the JSON data.
var xhr = new XMLHttpRequest();

// Where do we get the data?
xhr.open( 'GET', 'myjson.json', true );

// What do we do when we have it?
xhr.onreadystatechange = function() {

    // If we've received the data
    if ( xhr.readyState === 4 && xhr.status === 200 ) {

        // Parse the JSON
        var data = JSON.parse( xhr.responseText );

        // Tell the globe about your JSON data
        for ( var i = 0; i < data.length; i ++ ) {
            globe.addData( data[i][1], {format: 'magnitude', name: data[i][0]} );
        }

        // Create the geometry
        globe.createPoints();

        // Begin animation
        globe.animate();

    }

};

// Begin request
xhr.send( null );
```

# Starting a local development server

```
npm install
npm start
```

Navigate to http://localhost:3000 to see the demo.

Tested with Node 5.7 and npm 3.6.

**Wanna know some more regarding openmrs?**

**OpenMRS**
- OpenMRS is a collaborative open source project to develop software to support the delivery of health care in developing countries
- [OpenMRS](http://openmrs.org)

**OpenMRS Atlas**
- The OpenMRS Atlas is a website on which members of the OpenMRS Community can register their site(s).  The Atlas serves not only to let the world know about your site, but also help sites to discover other implementations in their region. 
- [OpenMRS Atlas](http://atlas.openmrs.org)

