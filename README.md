# Google Adwords Conversion Tracking Titanium Module

This Titanium module wraps the Google mobile Ads Conversion tracking for iOS SDK from:  
[https://developers.google.com/mobile-ads-sdk/docs/admob/conversion-tracking](https://developers.google.com/mobile-ads-sdk/docs/admob/conversion-tracking)

It was created as per the Appcelerator Titanium iOS Module Development Guide:  
[https://wiki.appcelerator.org/display/guides/iOS+Module+Development+Guide](https://wiki.appcelerator.org/display/guides/iOS+Module+Development+Guide)

using Titanium sdk version 3.5.1

## Installing this module

As per:  
[http://docs.appcelerator.com/titanium/latest/#!/guide/Using_Titanium_Modules](http://docs.appcelerator.com/titanium/latest/#!/guide/Using_Titanium_Modules),

download and unzip this module into your Titanium project:  
[https://github.com/iassael/adwords_conversion_tracking_titanium_module/raw/master/com.geoplus.adwordsconversiontracking-iphone-0.1.zip](https://github.com/iassael/adwords_conversion_tracking_titanium_module/raw/master/com.geoplus.adwordsconversiontracking-iphone-0.1.zip)

and then reference it in your tiapp.xml:

    <ti:app>
      <modules>
        <module version="0.1" platform="iphone">com.geoplus.adwordsconversiontracking</module>
      </modules>
    </ti:app>

## Using this module

    var adwords_tracker = require('com.geoplus.adwordsconversiontracking');
    if(!Ti.Android) {
      // A non-repeatable conversion event
      adwords_tracker.pingGoogle({
        conversionId: '< your id here >', 
        label:        '< your label here >',
        value:        '< your value here >',
        isRepeatable: false
      });

      // A repeatable conversion event
      adwords_tracker.pingGoogle({
        conversionId: '< your id here >', 
        label:        '< your label here >',
        value:        '< your value here >',
        isRepeatable: true
      });
    }