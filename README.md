# Resources for the C&amp;T iOS Coding Test

You will find JSON files that can act as fictional web services, along with fake product images.

## Coding Test

On this site you will find all the resources that you require for the test. 

### API

In the *api* folder you will find three api files.

Build your initial coding test against: api/search-valid-response.json for the main grid screen and api/product-search-response.json for the product details screen

If you get through the test quickly then you can point to the second api that causes some additional complexity in the data processing and parsing: api/search-valid-response-complex-price.json

#### Data - search-valid-response.json

This is the basic data for the product grid screen. The file contains a considerable amount of data, but for the test you are only interested in a small part.

Simply process the following properties:

* productId - This is the product id that should be used to retrieve the product information for the product details screen (even though the response is hard coded)
* price.now - This is a complex object but for the test we can assume that the price is in £s
* title - This is the title that should be used on the product grid page cell
* image - This is the image name that should be appended to the url to the images folder in this repo to retrieve the image to display in the product grid page cell

#### Data - search-valid-response.json

This is the basic data for the product details screen. The file contains a considerable amount of data, but for the test you are only interested in a small part.

Simply process the following properties:

* title - The title of the product
* media.images.urls[] - The image names that should be used to display in a scrollable gallery component on the product details screen
* price.now - The price is the product price in £s
* details.productInformation - The text to display in the product information
* displaySpecialOffer - When data is present here, this is shown on the product page under the price
* additionalServices.includedServices - Guarantee information
* code - The product code
* features[].attributes.name - The product specification name
* features[].attributes.value - The value for the product specification

#### Data - search-valid-response-complex-price

This is the basic data for the product grid screen. The file contains a considerable amount of data, but for the test you are only interested in a small part.

Simply process the following properties:

* productId - This is the product id that should be used to retrieve the product information for the product details screen (even though the response is hard coded)
* price.now - This is a complex object but for the test we can assume that the price is in £s
* title - This is the title that should be used on the product grid page cell
* image - This is the image name that should be appended to the url to the images folder in this repo to retrieve the image to display in the product grid page cell

So the main difference in this data set is that the "price.now" value can either be a String or the following:

```
{
   "from": "239.00",
   "to": "239.99"
}
```

### Images

The *json* data only provides you with the *image name*. You will need to append this to the url path to the *iamges* folder of this repo.

### Screen Designs

If you have time to build a UI during your test, then you can base the layout of your UI on the designs in the *screens* folder.

* ProductGrid.jpg - gives an idea of what the main page should look like
* ProductPagePortrait.jpg - gives an idea of what the details page should look like
* ProductPageLandscape.jpg - gives a possible alternative layout that could be used in the landscape orientation on iPad only, however it is not expected that you will have time for this

## Expectations

The aim of this test is for the applicant to write an iOS Application that sells Dishwashers. We would like to see the following

* The App should work on an iPad, in landscape and portrait mode.
* The code should be written in Swift 4
* The use of third party Code/SDKs is allowed, but you should be able to explain why you have chosen the third party.
* We’d like to see a TDD approach to writing the app, using XCTest.
* We expect the code to build and run using the latest version of Xcode that is currently available in the Apple App Store.

We’re not looking for a ‘pixel perfect’ app, we are looking at your style of coding, and how you’ve approached this.

