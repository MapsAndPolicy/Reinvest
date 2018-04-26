
<!DOCTYPE html>

<html>
<head>
<meta name=viewport content='width=700'>
<title>Community Reinvestment, Lucas County, Ohio</title>

   <!-- Material Design Lite -->
    <script src="https://storage.googleapis.com/code.getmdl.io/1.0.6/material.min.js"></script>
    <link rel="stylesheet" href="https://code.getmdl.io/1.1.1/material.blue_grey-blue.min.css" />
    <!-- Material Design icon font -->
    <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">

<!-- MDL Card -->
<style>
.SomeText-card-wide.mdl-card {
  width: 800px;
  margin: auto;
  margin-top: 35px;
}
</style>

<style>
.MapCard-card-wide.mdl-card {
  width: 90%;
  margin-right: 10px;
  margin-left: 35px;
  margin-top: 35px;
}
</style>

<style>
.MapButtons-card-wide.mdl-card {
  width: 500px;
  margin: 25px;
  margin-left: 35px;
  float: left;
  padding-top: 10px;
}
</style>

<style>
.MapToggles-card-wide.mdl-card {
    width: 530px;
    margin: 25px;
    margin-left: 35px;
    float: left;
    padding-right: 50px;
    padding-top: 10px;
}
</style>

<!--This is the Map Script Starting Here-->


<!--Google Analytics-->
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-83061052-1', 'auto');
  ga('send', 'pageview');

</script>

<!--Set up map settings, etc.-->
    <style>
      html, body, #map-canvas {
        height: 550px;
        width: 100%;
        margin: 0px;
        padding: 0px
      }
      .controls {
        margin-top: 16px;
        border: 1px solid transparent;
        border-radius: 2px 0 0 2px;
        box-sizing: border-box;
        -moz-box-sizing: border-box;
        height: 32px;
        outline: none;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
      }

      #pac-input {
        background-color: #fff;
        padding: 0 11px 0 13px;
        width: 350px;
        font-family: Roboto;
        font-size: 15px;
        font-weight: 300;
        text-overflow: ellipsis;
      }

      #pac-input:focus {
        border-color: #4d90fe;
        margin-left: -1px;
        padding-left: 14px;  /* Regular padding-left + 1. */
        width: 401px;
      }

      .pac-container {
        font-family: Roboto;
      }

      #type-selector {
        color: #fff;
        background-color: #4d90fe;
        padding: 5px 11px 0px 11px;
      }

      #type-selector label {
        font-family: Roboto;
        font-size: 13px;
        font-weight: 300;
      }

}
    </style>

    <script src="https://maps.googleapis.com/maps/api/js?v=3.exp&libraries=places" "https://maps.googleapis.com/maps/api/js?key=AIzaSyC9-oksn15mPcHX8HM-sHcjnYFc_FsPJGY&callback=initMap"></script>

<!--This Function - imediately below - is set up for Radio buttons so that other layers are removed when you select a layer-->
<!--But, if you wanted to set up the function to keep multiple layers on the map, it would look like this:-->
<!--
function toggleLayer(this_layer){
  if(this_layer.getMap()) {
   this_layer.setMap(null)
  } else {
   this_layer.setMap(map);
  }
}
-->

  <script type="text/javascript">
    function toggleLayer(this_layer){
    layer_1.setMap(null);
    layer_2.setMap(null);
    layer_3.setMap(null);
    layer_4.setMap(null);
    layer_6.setMap(null);
    layer_7.setMap(null);
    layer_9.setMap(null);
    layer_10.setMap(null);
    layer_11.setMap(null);
    layer_12.setMap(null);
    this_layer.setMap(map);
    }

//ThisFunction clears the first layers
    function toggleLayer50(this_layer){
    layer_1.setMap(null);
    layer_2.setMap(null);
    layer_3.setMap(null);
    layer_4.setMap(null);
    layer_6.setMap(null);
    layer_7.setMap(null);
    layer_9.setMap(null);
    layer_10.setMap(null);
    layer_11.setMap(null);
    layer_12.setMap(null);
    layer_13.setMap(null);
    layer_14.setMap(null);
    layer_15.setMap(null);
    }

//<!-- ThisFunction is for the first set of unique data-->
    function toggleLayer100(this_layer){
    layer_102.setMap(null);
    layer_103.setMap(null);
    layer_104.setMap(null);
    this_layer.setMap(map);
    }

//ThisFunction is for the second set of unique data
    function toggleLayer200(this_layer){
    layer_100.setMap(null);
    layer_101.setMap(null);
    layer_104.setMap(null);
    this_layer.setMap(map);
    }

//ThisFunction is for the third set of unique data
    function toggleLayer300(this_layer){
    layer_100.setMap(null);
    layer_101.setMap(null);
    layer_103.setMap(null);
    this_layer.setMap(map);
    }

//<!-- ThisFunction desgined to clear out the toggleLayer100s maps-->
    function toggleLayer1000(this_layer){
        layer_100.setMap(null);
        layer_101.setMap(null);
        layer_102.setMap(null);
        layer_103.setMap(null);
        layer_104.setMap(null);
    }

//This function provides an alternatve set of unique data. Here, I'm adding in data on banking activity. For this set, I'll make the display all at once and not mutually exclusive. I'll use checkboxes instead of radio buttons later in the body. 
      
    function bankData()
 {
     if(document.getElementById('Banks').checked)
         {layer_2000.setMap(map);}
     else 
         {layer_2000.setMap(null);}

     if(document.getElementById('Short-TermLenders').checked)
         {layer_2001.setMap(map);}    
     else 
         {layer_2001.setMap(null);}
     
     if(document.getElementById('CreditUnions').checked)
         {layer_2002.setMap(map);}
     else
         {layer_2002.setMap(null);}
     
     if(document.getElementById('auto-title').checked)
         {layer_2003.setMap(map);}
     else
         {layer_2003.setMap(null);}
     
     if(document.getElementById('SecondMortgage').checked)
         {layer_2004.setMap(map);}
     else
         {layer_2004.setMap(null);}
     
     if(document.getElementById('CSO').checked)
         {layer_2005.setMap(map);}
     else
         {layer_2005.setMap(null);}     
 }
      
//This function will clear out the banking data. I'm not sure if I'll use this though since you can just turn them on and off with the checkboxes. 
    function toggleLayer2500(this_layer){
          layer_2000.setMap(null);
          layer_2001.setMap(null);
          layer_2002.setMap(null);
          layer_2003.setMap(null);
          layer_2004.setMap(null);
          layer_2005.setMap(null);
      }

function initialize() {

  var markers = [];
  map = new google.maps.Map(document.getElementById('map-canvas'), 
  
  {
    center: new google.maps.LatLng(41.61383518331377, -83.60232580566405),
    zoom: 11,
    zoomControl: true,
    zoomControlOptions: {
        position: google.maps.ControlPosition.LEFT_TOP
    }, 
    
    // STYLING!.
styles: [
    {
    "featureType": "administrative.province",
    "elementType": "geometry.stroke",
    "stylers": [
      { "visibility": "on" },
      { "color": "#808080" },
      { "weight": 2.3 },
      { "lightness": -19 }
    ]
  },{
    "featureType": "road.highway",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "lightness": 24 },
      { "color": "#3a79ec" },
      { "weight": 0.7 }
    ]
  },{
    "featureType": "road.local",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "color": "#808080" },
      { "weight": 0.3 },
      { "lightness": -30 }
    ]
  },{
    "featureType": "road.arterial",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "color": "#8099e3" },
      { "lightness": -9 },
      { "weight": 0.3 }
    ]
  },{
  },{
    "featureType": "landscape.man_made",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "color": "#808080" },
      { "lightness": 81 }
    ]
  },{
    "featureType": "landscape.natural",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "color": "#80d880" },
      { "lightness": 72 }
    ]
  },{
    "featureType": "poi.park",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "saturation": 18 },
      { "color": "#80c580" }
    ]
  },{
    "featureType": "poi.medical",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "color": "#e68080" },
      { "saturation": 76 }
    ]
  },{
    "featureType": "poi.government",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "color": "#808080" },
      { "lightness": -13 }
    ]
  },{
    "featureType": "poi.school",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "hue": "#eeff00" },
      { "saturation": 93 },
      { "gamma": 0.7 }
    ]
  },{
    "featureType": "poi.attraction",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "saturation": 84 },
      { "gamma": 0.72 },
      { "hue": "#00ff00" },
      { "lightness": -4 }
    ]
  },{
    "featureType": "poi.business",
    "elementType": "geometry.fill",
    "stylers": [
      { "visibility": "on" },
      { "lightness": -13 },
      { "color": "#a78080" }
    ]
  },{
    "featureType": "road.arterial"  }
]
// End styling
    
  });
  
   // Note - This is the Opportunity Zone Layer
  layer_1 = new google.maps.FusionTablesLayer({
    query: {
      select: "col19",
      from: "1xIUmA-EOO8-2RdtnA786bqjwOytPl_SCsSc-VSds"
    },
    styleId: 4,
    templateId: 5
  });
   // Note - This is the LMI percent layer
      layer_2 = new google.maps.FusionTablesLayer({
        query: {
          select: "col26",
          from: "1oAMVkVMcC5F94kGd2emLax38G3djQKtXLmXBV-gi"
        },
        styleId: 2,
        templateId: 2
      });
   // Note - This is the USDA Food Desert Layer
       layer_3 = new google.maps.FusionTablesLayer({
        query: {
          select: "col74",
          from: "1dNQjUTDr3v-EBhOeXPN8j_lGIJfADLwlT72KNVso"
        },
        styleId: 2,
        templateId: 2
      });
   // Note - This is the 5% or more African-American Layer
       layer_4 = new google.maps.FusionTablesLayer({
        query: {
      select: "col21",
      from: "1e8r5ammd1LYcZqK3xPP81lbeHB6vE9KSQSidO791"
        },
        styleId: 2,
        templateId: 2
      });

   // Note - This is the City of Toledo's Code Enforcement Layer
       layer_6 = new google.maps.FusionTablesLayer({
        query: {
          select: "col11",
          from: "1ZEagjCF5hgtQ80Wow4vUJHf_qbyEqDrlWyOcWbGO"
        },
        styleId: 2,
        templateId: 2
      });
   // Note - This is the NHPD LIHTC Layer
       layer_7 = new google.maps.FusionTablesLayer({
        query: {
          select: "col13",
          from: "1SwWULn9-bSoLzGjdzCmWYSZJpc0QSwrBuqFJR6ib"
        },
        styleId: 2,
        templateId: 2
      });

   // Note - This is the MRFEI layer
       layer_9 = new google.maps.FusionTablesLayer({
        query: {
          select: "col23",
          from: "1ohPS9qBmGxxb2wjXVVcMvqFNsRZvf9EdocGn80uA"
        },
        styleId: 2,
        templateId: 2
      });

    //Note - This is the Median Year Structure Built Layer 
  layer_10 = new google.maps.FusionTablesLayer({
    query: {
      select: "col18",
      from: "1Tld-wsHVrVErh4WF03e3dQK79b4NrOHi_kpJqfTI"
    },
    styleId: 2,
    templateId: 2
  });    

    //Note - This is the Toledo Municipal Boundary Line
  layer_11 = new google.maps.FusionTablesLayer({
    query: {
      select: "col18",
      from: "1SXVfEuORrIW0ro10ur24c6nGYm0zCvbHoqE_4dQ6"
    },
    styleId: 2,
    templateId: 2
  });    

    //Note - This is the Percent Renter layer
  layer_12 = new google.maps.FusionTablesLayer({
    query: {
      select: "col24",
      from: "1r4ibHpfuR8CJcnReIt8n99U3URsCyNJBL-suhghS"
    },
    styleId: 2,
    templateId: 2
  });    

//Note - This is the City Council Districts Layer
  layer_12 = new google.maps.FusionTablesLayer({
    query: {
      select: "col7",
      from: "1EbvhPEAyPY8dL4OPZkyfnRy6712qxqBwPmvqbpqJ"
    },
    styleId: 2,
    templateId: 2
  });    
    
    
    
   // This section for unique data sets
   // Note - This is the Total Asthma Centroids Layer
       layer_100 = new google.maps.FusionTablesLayer({
        query: {
          select: "col22",
          from: "1mNQmT2WYyiBkLzn5Anfjaf6Wvn95ltaFMHsdamp7"
        },
        styleId: 2,
        templateId: 2
      });

   // Note - This is the Total Asthma Centroids Layer
       layer_101 = new google.maps.FusionTablesLayer({
        query: {
          select: "col40",
          from: "1PMovltEojRBynHDTdW_GW0BHnK0aSFYG7Xjpj2w4"
        },
        styleId: 2,
        templateId: 2
      });

   // Note - This is the blank Census tracts layer
       layer_102 = new google.maps.FusionTablesLayer({
        query: {
          select: "col9",
          from: "1LXu8-OVMiHs8s6cqwQ0u_ZpJipo_3b7hfMqHr6Gm"
        },
        styleId: 2,
        templateId: 2
      });
        
   // Note - This is the Mold Trigger Centroid Layer
       layer_103 = new google.maps.FusionTablesLayer({
        query: {
          select: "col14",
          from: "1TXc6kvT--Zziui-DxjWLKhEwme-IMh-AA7mGiZo7"
        },
        styleId: 2,
        templateId: 2
      });

   //Note - This is the Cockroach Trigger Centroid Layer
       layer_104 = new google.maps.FusionTablesLayer({
        query: {
          select: "col14",
          from: "1MSh3eydCza3UbXCuvZY3zz03BnLV0Zsy3l5bB1y4"
        },
        styleId: 2,
        templateId: 2
      });
    
    //Note - This is the Bank Locations Layer
       layer_2000 = new google.maps.FusionTablesLayer({
        query: {
          select: "col13",
          from: "1CKLD3-10ZGIsyKb0VOsCa7eD3Vr5ibAMFai-eyA6"
        },
        styleId: 2,
        templateId: 2
      });

    //Note - This is the ALL Pay Day and Short-Term Lenders layer
       layer_2001 = new google.maps.FusionTablesLayer({
        query: {
          select: "col22",
          from: "10VbtkGalD9agsuSjnEujlE0F-Ng7EjyPnlyx8CXH"
        },
        styleId: 2,
        templateId: 2
      });
    
    //Note - This is the Credit Unions Layer
       layer_2002 = new google.maps.FusionTablesLayer({
        query: {
          select: "col19",
          from: "1feC2_LT-NdW8V7RR8oeFi6SIE01SMxeEmaZh6OGv"
        },
        styleId: 2,
        templateId: 2
      });
    
    //Note this is the auto-title layer
        layer_2003 = new google.maps.FusionTablesLayer({
            query: {
                select: "col4",
                from: "1FQB88g3wUfLZ3_H8bOA_LzktXMoRSPc-20TbnYv2"
            },
            styleId: 2, 
            templateId: 2
        });
    
    //Note this is the Second Mortgage Layer
       layer_2004 = new google.maps.FusionTablesLayer({
            query: {
                select: "col17",
                from: "1p41UWkQgE3-3EuyyUCpmtgTZZhk5N17sEUJ6VGUn"
            },
            styleId: 2, 
            templateId: 2
        });
    
    //Note this is the CSO
       layer_2005 = new google.maps.FusionTablesLayer({
            query: {
                select: "col17",
                from: "1U5B0Ng5VaD3XrnU-rcQcCsDTwXnepCBHCXEixrXW"
            },
            styleId: 2, 
            templateId: 2
        });
    

  var input = /** @type {HTMLInputElement} */(
      document.getElementById('pac-input'));
  map.controls[google.maps.ControlPosition.TOP_LEFT].push(input);

  var searchBox = new google.maps.places.SearchBox(
    /** @type {HTMLInputElement} */(input));

  // [START region_getplaces]
  // Listen for the event fired when the user selects an item from the
  // pick list. Retrieve the matching places for that item.
  google.maps.event.addListener(searchBox, 'places_changed', function() {
    var places = searchBox.getPlaces();

    if (places.length == 0) {
      return;
    }
  // You would add this Code if you wanted to clear out old markers but i've chosen to keep all markers so users can add a series of thier own markers:
  // for (var i = 0, marker; marker = markers[i]; i++) {
  //  marker.setMap(null);
  // }

    // For each place, get the icon, place name, and location.
    markers = [];
    var bounds = new google.maps.LatLngBounds();
    for (var i = 0, place; place = places[i]; i++) {
      var image = {
        url: place.icon,
        size: new google.maps.Size(71, 71),
        origin: new google.maps.Point(0, 0),
        anchor: new google.maps.Point(17, 34),
        scaledSize: new google.maps.Size(25, 25)
      };

      // Create a marker for each place.
      var marker = new google.maps.Marker({
        map: map,
        icon: image,
        title: place.name,
        position: place.geometry.location
      });

      markers.push(marker);

      bounds.extend(map);
    }
    map.fitBounds(bounds);
  });
  
  // [END region_getplaces]

  google.maps.event.addListener(map, 'bounds_changed', function() {
    var bounds = map.getBounds();
    searchBox.setBounds(bounds);
  });
}

google.maps.event.addDomListener(window, 'load', initialize);
    </script>

<style>
.SecondLine {
    margin-left: 35px;
}
</style>

</head>
<body>
    


<div class="MapButtons-card-wide mdl-card mdl-shadow--2dp">
    
  <div style="text-align: center"><b>Demographic Map Layers</b></div>
        <ul style="list-style-type:none">

<!--This is the LMI percent checkbox-->
          <li><label class="mdl-radio mdl-js-radio mdl-js-ripple-effect" for="show_hide_layer_2"><input type="radio" class="mdl-radio__button" name="DemographicInfo" id="show_hide_layer_2" onclick="toggleLayer(layer_2)"/>Percent Percent Low to Moderate Income (LMI) families. Darker shades indicate a larger percent of LMI families</label></li>  

<!--This is the 5% or more African-American Layer--> 
      <li><label class="mdl-radio mdl-js-radio mdl-js-ripple-effect" for="show_hide_layer_4"><input type="radio" class="mdl-radio__button" name="DemographicInfo" id="show_hide_layer_4" onclick="toggleLayer(layer_4)"/>Percent African-American popluation (five percent or more)</label></li>
            
<!--This is the Toledo Municipal Boundaries Layer-->
      <li><label class="mdl-radio mdl-js-radio mdl-js-ripple-effect" for="show_hide_layer_11"><input type="radio" class="mdl-radio__button" name="DemographicInfo" id="show_hide_layer_11" onclick="toggleLayer(layer_11)"/>City of Toledo municipal boundary line</label></li>
      
<!--This is the City Council Districts Layer-->
<li><label class="mdl-radio mdl-js-radio mdl-js-ripple-effect" for="show_hide_layer_12"><input type="radio" class="mdl-radio__button" name="DemographicInfo" id="show_hide_layer_12" onclick="toggleLayer(layer_12)"/>City of Toledo, City Council Districts</label></li>    
    
    </ul> 
<!--this is the button to clear out the other layers-->   
      <div style="text-align: center"><button class="mdl-button mdl-js-button mdl-button--raised mdl-js-ripple-effect" onclick="toggleLayer50()"> Clear Layer </button></div>
      <br>
</div>   
   
<div class="MapToggles-card-wide mdl-card mdl-shadow--2dp">

    <div style="text-align: center"><b>Short-term lenders</b></div>
<ul style="list-style-type:none">
    
<li><label class="mdl-switch mdl-js-switch mdl-js-ripple-effect" for="Short-TermLenders">
  <input type="checkbox" id="Short-TermLenders" class="mdl-switch__input" onclick="bankData()"><span class="mdl-switch__label">
    Payday and other short-term lenders</span>
    </label></li><br>

    <li>Lenders include businesses that issue high-intrest small loans with excessive fees, including those that hold checks until payday, and lenders that issue loans based on a title to an automobile other than for the purchase of an automobile. Data is based on licensing information from Ohio's Department of Financial Institutions as well as Reference USA as of June, 2016. This data may not be all-inclusive and the number and location of payday lenders may change over time.</li>
    
<!--this is the button to clear out the other layers   
      <div style="text-align: center"><button class="mdl-button mdl-js-button mdl-button--raised mdl-js-ripple-effect" onclick="toggleLayer1000()"> Clear Layer </button></div>
      <br>
-->
          </ul>
          </div>
          
    <div class="MapCard-card-wide mdl-card mdl-shadow--2dp">
 
   <div id="map-canvas"></div>
    <input id="pac-input" class="controls" type="text" placeholder="Search">

</div>   
<br>
<div class="MapToggles-card-wide mdl-card mdl-shadow--2dp">

    <div style="text-align: center"><b>Additional layers</b></div>
<ul style="list-style-type:none">
    
<li><label class="mdl-switch mdl-js-switch mdl-js-ripple-effect" for="Banks">
  <input type="checkbox" id="Banks" class="mdl-switch__input" onclick="bankData()"><span class="mdl-switch__label">
  Standard bank branch locations as of June, 2015
    </span></label></li><br>
            
<li><label class="mdl-switch mdl-js-switch mdl-js-ripple-effect" for="CreditUnions">
  <input type="checkbox" id="CreditUnions" class="mdl-switch__input" onclick="bankData()">
    <span class="mdl-switch__label">Credit union branch locations as of February, 2016</span>
    </label></li><br>
               
<!--this is the button to clear out the other layers   
      <div style="text-align: center"><button class="mdl-button mdl-js-button mdl-button--raised mdl-js-ripple-effect" onclick="toggleLayer1000()"> Clear Layer </button></div>
      <br>
-->
          </ul>
          </div>

        
        

    
    
<!--Unique Datasets
      <li><label class="mdl-radio mdl-js-radio mdl-js-ripple-effect" for="show_hide_layer_100"><input type="radio" class="mdl-radio__button" name="UniqueData" id="show_hide_layer_100" onclick="toggleLayer100(layer_101);toggleLayer100(layer_100)"/>Total Asthma Incidents Centroid - Census Block Group</label></li>
      
      <li><label class="mdl-radio mdl-js-radio mdl-js-ripple-effect" for="show_hide_layer_102"><input type="radio" class="mdl-radio__button" name="UniqueData" id="show_hide_layer_102" onclick="toggleLayer200(layer_102);toggleLayer200(layer_103)"/>Total Mold Trigger Incidents Centroid - Census Tract</label></li>
      
      <li><label class="mdl-radio mdl-js-radio mdl-js-ripple-effect" for="show_hide_layer_104"><input type="radio" class="mdl-radio__button" name="UniqueData" id="show_hide_layer_104" onclick="toggleLayer300(layer_102);toggleLayer300(layer_104)"/>Total Cockroach Trigger Incidents Centroid - Census Tract</label></li>
-->
      

<br>
<br>

    
</body>
</html>
