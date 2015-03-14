<h1> Java API for Google geocoder v3 </h1>
<h3>Maven</h3>
<h4>Repository</h4>

Now artifact deployed to central repository

<h4>Artifact</h4>
```
<dependencies>
  <dependency>
    <groupId>com.google.code.geocoder-java</groupId>
    <artifactId>geocoder-java</artifactId>
    <version>0.16</version>
  </dependency>
  <!-- ... -->
</dependencies>
```

<h4>Direct Download</h4>

http://repo1.maven.org/maven2/com/google/code/geocoder-java/geocoder-java/
<h4>Dependencies</h4>
**required**
```
com.google.code.gson:gson:2.2.4
org.slf4j:slf4j-api:1.7.7
```

**optional**
```
commons-httpclient:commons-httpclient:3.1
```

<h3>Usage</h3>
<h4>Simple</h4>
```
final Geocoder geocoder = new Geocoder();
GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

<h4>Google Map API Premier</h4>
```
final Geocoder geocoder = new Geocoder("clientId","clientKey");
GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

<h4>via Proxy</h4>
```
HttpClient httpClient = new HttpClient(new MultiThreadedHttpConnectionManager());
httpClient.getHostConfiguration().setProxy("85.25.109.152", 3128);

Geocoder geocoder = new AdvancedGeoCoder(httpClient);GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

<h4>with timeout</h4>
```
HttpClient httpClient = new HttpClient(new MultiThreadedHttpConnectionManager());
httpClient.getParams().setParameter(HttpMethodParams.SO_TIMEOUT, 60 * 1000); //60s

Geocoder geocoder = new AdvancedGeoCoder(httpClient);GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

<h4>with GAE</h4>
```
final Geocoder geocoder = new Geocoder();
GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```