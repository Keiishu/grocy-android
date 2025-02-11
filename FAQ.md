<a name="pagetop"></a>
# Grocy Android Support

If you have a question, please check the frequently asked questions below first.
At the bottom, you can find out how to ask other questions, request features, and report bugs.

Credits for the layout and some text of this FAQ go to [M66B](https://github.com/M66B) and his [FairEmail](https://github.com/M66B/FairEmail) repo.

## Index

* [How to](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-howto)
* [Planned features](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-planned-features)
* [Frequently Asked Questions](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-frequently-asked-questions)
* [Support](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-support)

<a name="howto">

## How to

<a name="howto-consume"></a>
**How to consume a product?**

Every time you consume something, you consume it in Grocy as well.
Ways to consume a product:

- Stock overview: search for the product, swipe right on it and tap the CONSUME icon.
- Stock overview: search for the product, tap on it to open the product overview, then tap the CONSUME icon.
- Tap the green button in stock overview to go into scan mode, make sure you are in CONSUME mode, then scan your product.
- Tap on the CONSUME shortcut of Grocy in your app launcher (since Android 7.1) and scan your product.
- Open the CONSUME page in the bottom drawer and fill out the form, then tap the green button.

<br />

<a name="howto-open"></a>
**How to mark a product as opened?**

Every time you open or broach something, you mark one of it in Grocy as open.
Ways to mark a product as opened:

- Stock overview: search for the product, swipe right on it and tap the OPEN icon.
- Stock overview: search for the product, tap on it to open the product overview, then tap the OPEN icon.
- Tap the green button in stock overview to go into scan mode, tap the CONSUME label to switch to MARK AS OPENED, then scan your product.
- Tap on the CONSUME shortcut of Grocy in your app launcher (since Android 7.1) and continue as described previously.
- Open the CONSUME page in the bottom drawer and fill out the form, then tap the OPEN icon in the bottom bar.

<br />

## Planned features

* Recipes
* Mealplans

Anything on this list is in random order and *might* be added in the near future.

## Frequently Asked Questions

* [(1) Which permissions are needed and why?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq1)
* [(2) How do I know what something does?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq2)
* [(3) My API key is invalid. What can I do?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq3)
* [(4) How can I use this app with Hass.io?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq4)
* [(5) Why are my barcodes unreadable if I use the selfie camera?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq5)
* [(6) What is ML Kit barcode scanner?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq6)
* [(7) How can I connect to my instance through Tor Hidden Service or Proxy?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq7)
* [(8) How can I use my USB or Bluetooth™ barcode scanner device?](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq8)

[I have another question.](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-support)

<br />

<a name="faq1"></a>
**(1) Which permissions are needed and why?**

The following Android permissions are needed:

* *have full network access* (INTERNET): to access your grocy server
* *view network connections* (ACCESS_NETWORK_STATE): to monitor internet connectivity changes
* *have camera access* (CAMERA): to scan barcodes
* *have access to vibration* (VIBRATE): to vibrate after a barcode was detected

<br />

<a name="faq2"></a>
**(2) How do I know what something does?**

Starting with Android 8 you can long press almost every clickable element without a label to see what it will do.

<br />

<a name="faq3"></a>
**(3) My API key is invalid. What can I do?**

Tap CREATE KEY to open the key management page of your Grocy instance.
Create a new key and copy it to your clipboard, then paste it in the key field of Grocy Android and try again.

If you use Hass.io with the Grocy Add-on, read [this](https://github.com/patzly/grocy-android/blob/master/FAQ.md#user-content-faq4) section.

<br />

<a name="faq4"></a>
**(4) How can I use this app with the grocy Home Assistant add-on?**

*In the v2.0.0 beta version of our app you can login with a long-term token from Home Assistant (together with a grocy API key). You won't need to open a port then anymore.
  To set it up, you can scan a QR code from the grocy API keys page. If this doesn't work you can enter the data manually: Enter your IP address with the according port (e. g. 8123). Get a long lived access token from your Home Assistant and an API key from your Grocy instance. To get the ingress instance name, go into Grocy -> Settings -> REST-API browser. In the window which opened, select the part of the URL between /hassio_ingress/ and /api/. That´s your ingress instance.*

In the Supervisor of Hass.io, open the Configuration tab of the Grocy Add-on.
Change the host port (which will be exposed) from "null" to any other number like "40" (without the quotes) in the Network section.
Now in this app here in the field "Server URL", enter the domain or IP address of your Hass.io server together with ":" and the chosen port number.
So the Server URL can look like this:

- `http://192.168.178.123:40`
- `https://myhassioserver.com:40`

Attention! If your Hass.io server is publicly accessible, following points are important for you:

- Make sure that you have set up a working HTTPS certificate in the Configuration section of the Grocy Add-on.
- Start the URL with "https://" like above.
- Set a strong password for all users in Grocy (default is "admin"), because anyone has now access to your Grocy instance and it is not protected by Hass.io login anymore.

<br />

<a name="faq5"></a>
**(5) Why are my barcodes unreadable if I use the selfie camera?**

Most devices have a front camera with a fixed focus for the normal distance between your face and the device.
With this distance, the picture resolution is sometimes too low for the scanning algorithm.

<br />

<a name="faq6"></a>
**(6) What is ML Kit barcode scanner?**

ML Kit is an alternative AI-based barcode scanner which is implemented in the Google Play and GitHub version of our app since v2.0.0, F-Droid doesn't allow closed-source app components and thus we can't offer the same version there. ML Kit is from Google and doesn't make recognition mistakes compared to ZXing (the primary scanner option in our app). Additionaly, you don't have to align the barcode horizontally in your camera because it recognizes barcodes with any orientation. Go to `app settings -> Scanner -> Barcode scanner` to use ML Kit. You can either purchase the required unlock app in Google Play Store (which would make us happy) or you can download the unlock APK [here](https://github.com/patzly/grocy-android-unlock).

<br />

<a name="faq7"></a>
**(7) How can I connect to my instance through Tor Hidden Service or Proxy?**

Go to `app settings -> Network` and enable Tor support or HTTP-Proxy. Orbot is required for Tor support.

<br />

<a name="faq8"></a>
**(8) How can I use my USB or Bluetooth™ barcode scanner device?**

Go to `app settings -> Scanner` and enable support for external scanners. Then you can connect a scanner for example using USB or Bluetooth™ and use it on the purchase/consume/transfer/inventory pages (the product field must be focused). Your scanner should have TAB or Enter as suffix, otherwise the workflow won't start after a scan.

## Support

Please go to our [project page](https://github.com/patzly/grocy-android) on GitHub and open a new issue with your question.
We will try to help you as fast as possible.
