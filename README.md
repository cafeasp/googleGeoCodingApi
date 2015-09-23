# Google Geo Coding Api Demo
Geocoding is the process of converting addresses (like "1600 Amphitheatre Parkway, Mountain View, CA") into geographic coordinates (like latitude 37.423021 and longitude -122.083739), which you can use to place markers on a map, or position the map.
This code is base on Google https://developers.google.com/maps/documentation/geocoding/intro using basic javascript and I will use .net on the backend/server.

To use the Google Maps Geocoding API, you need an API key.

This project will include a library class that will give you a way to start your own projects. Google gives the option to output XML or JSON. I would recommend to use JSON as you make request to the api.

How to use it:

            var g = new vpGeo();
            g.Key = myAPiKey;
            var r = g.GoogleGeoCodeInfo(new Address { Address1 = address, City = city, State = state, Zip = zip });
            if (g.GeoResult == vpGeo.Result.OK)
            {
                return Json(new {lat=decimal.Parse(r.Result[0].Geometry.Location.Lat),lon=decimal.Parse(r.Result[0].Geometry.Location.Long)});
            }
            
<b>Remember:</b> this is for testing only. Make your own adjustments.
