# Java API for Google geocoder v3
### Maven
#### Repository

Now artifact deployed to central repository

#### Artifact
```xml
<dependencies>
  <dependency>
    <groupId>com.google.code.geocoder-java</groupId>
    <artifactId>geocoder-java</artifactId>
    <version>1.0.0</version>
  </dependency>
  <!-- ... -->
</dependencies>
```

#### Direct Download

http://repo1.maven.org/maven2/com/google/code/geocoder-java/geocoder-java/
<h4>Dependencies</h4>
*required*
```
com.google.code.gson:gson:2.2.4
org.slf4j:slf4j-api:1.7.7
```

*optional*
```
commons-httpclient:commons-httpclient:3.1
```

### Usage
#### Simple
```java
final Geocoder geocoder = new Geocoder();
GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

#### Google Map API Premier Using Client ID
```java
final Geocoder geocoder = new Geocoder("clientId","clientKey");
GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

#### Google Map API Premier Using API Key
```java
final Geocoder geocoder = new Geocoder("key");
GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

#### via Proxy
```java
HttpClient httpClient = new HttpClient(new MultiThreadedHttpConnectionManager());
httpClient.getHostConfiguration().setProxy("85.25.109.152", 3128);

Geocoder geocoder = new AdvancedGeoCoder(httpClient);GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

#### with timeout
```java
HttpClient httpClient = new HttpClient(new MultiThreadedHttpConnectionManager());
httpClient.getParams().setParameter(HttpMethodParams.SO_TIMEOUT, 60 * 1000); //60s

Geocoder geocoder = new AdvancedGeoCoder(httpClient);GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```

#### with GAE
```java
final Geocoder geocoder = new Geocoder();
GeocoderRequest geocoderRequest = new GeocoderRequestBuilder().setAddress("Paris, France").setLanguage("en").getGeocoderRequest();
GeocodeResponse geocoderResponse = geocoder.geocode(geocoderRequest);
```
