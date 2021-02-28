# Improvement Suggestions For Imagify
<br><br>
## Suggestions to add to the Support Wishlist

https://github.com/wp-media/imagify/issues/898 - Allow to search users by name, surname, or partial email

https://github.com/wp-media/imagify/issues/714 - When scheduling a cancellation, quota is reset when it shouldn't

https://github.com/wp-media/imagify/issues/886 - Allow admins to increase available quota by any value


<br><br>
## Suggestions for Media Library Page

### Improve display of Optimization Info for Each Image
<img src="https://i.imgur.com/viNffOx.jpg">

- Above is a potential new way optimization information could be laid out for users
  - I think it organizes info in a way that's more intuitive for users, and is more concise

- The first listing is how information is currently listed

- The second one is how a listing could appear without the details expanded
  - Shows more information in same amount of space
  - I think users mostly want to know how much filesize savings they're getting, both in terms of the original filesize and the overall filesize, so I make both of these values visible along with the percentage savings

- The third one shows a successfully optimized image expanded to show all details
  - Also allows options to restore to original and to re-optimize to different levels of compression

- The fourth one shows how for images that need them, links for "Generate Missing WebP Images" or "Optimize Missing Thumbnails" links could be displayed
  - Also shows how space at the bottom could be used to display any notes or messages needed about a particular image

- The fifth one shows how the WELL DONE... images could be displayed differently
  - When I first saw a "WELL DONE" image, I thought it meant something was wrong. I think this impression is given because the layout is different than the layout for successfully optimized images (it's more similar to error messages in my opinion) and also the "Try Again" button implies that it's necessary to try again for some reason
    - Example: https://wordpress.org/support/topic/difference-in-display-2/
  - This suggested layout gives less the impression that something is wrong, but instead just that no compression was needed at the current level, and it also gives them the option to try optimization at a different level if they want.
  - If needed, could also display a "Generate Missing WebP Images" too, which is more intuitive for users than the "Try Again" button.

- One other point of confusion (that is not addressed in the image above) is that users often are confused that the "New Filesize" value is the file size of the WebP version when WebP creation is enabled. I've had many tickets where users are confused why the size of the image displayed on their page is different than the "New Filesize" value (happens when the jpg/png version is being displayed rather than the WebP version).

### When optimization is hanging in Media Library on images, would be nice to have a way to stop it
- Frustrating for users when it's just hanging on the "Optimizing..." for many minutes without a way for them to stop it
- Would also be nice for while we are testing different things to be able to stop optimization


<br><br>
## Suggestion for Upgrades / Downgrades
Lay out all credits, prorated charges, and the final amount user will be charged for upgrade/downgrade during the checkout process:
### Upgrades
- Credit amount for unused portion of former plan
- Prorated charge for remainder of billing period on new plan
- Actual amount will be charged for upgrade
- Normal payment going forward
### Downgrades
- Credit amount for unused portion of former plan
- Prorated charge for remainder of billing period on new plan
- Amount of credit left on account after accounting for the 2 above values
- Normal payment amount after credit used


<br><br>
## Could We Possibly Change How Updates Are Charged?
https://secure.helpscout.net/conversation/1426138959/239537/
https://wp-media.slack.com/archives/C7CTJKAA2/p1614062521002000
- When upgrading from monthly to yearly, the charge is made immediately
- But if upgrading from Growth monthly to Infinite monthly, the charge is not made immediately
- This causes confusion and frustration because users usually think the charge is being applied immediately, so when their next payment is larger than they expect, they don't understand why
- Also, if they happen to cancel that same month, they still end up getting charged for the upgrade at the end after they've unsubscribed and they get mad about the charge
- They may also delete their card or PayPal billing agreement in the meantime and then we end up not getting the money for the upgrade at all.


<br><br>
## Cannot Switch PayPal Payments From Monthly to Yearyl or Vice Versa
- Is this fixable from our end in any way?
- Might involve process where making this change in Imagify profile does the following in Braintree:
    - Cancel current subscription
    - Create new subscription with new billing period (monthly or yearly) while charging only the amount for the upgrade minus the remaining value from previous plan


<br><br>
## Offer Better Optimization Error Messages
- Is there any way to prevent cURL error 28 errors or timeouts during optimization from giving the error message that users are out of credit?
    - It leads to them buying more quota when they don't need it, or getting frustrated that they just bought a plan and think they've already run out of quota.
    

<br><br>
## Bulk Optimizer Page Potential Improvements


### Make the quota used / quota left guage more consistent across the App and the plugin

- Displays in the App as follows:
<img src="https://i.imgur.com/VhNgfuG.jpg">

- Displays in the plugin as follows:
<img src="https://i.imgur.com/UKQ31aA.jpg">

- Might be good to also display the 32.04 / 525MB used to make the experience more consistent


### Make it clear to users that when the Bulk Optimizer is run multiple times, images that are already optimized are not re-optimized

- Users often get the sense their quota is being wasted optimizing images that have already been optimzed when running Bulk Optimizer multiple times

- Could state somewhere on the Bulk Optimization page that images already optimized at current level will not be re-optimized if you run Bulk Optimizer multiple times

- I think the following may also contribute to this feeling from users. In this example, user has 8 images listed as already being optimized
<img src="https://i.imgur.com/1SSLMxl.jpg">

- But when you click "Imagif'em All" that number goes back down to 0, giving the impression that the 8 images may be being re-optimized
<img src="https://i.imgur.com/wcRIrw3.jpg">

- Instead, it may be better for this number to remain the same, and only increase if more images get optimized. The percentage could still start at 0% giving an indication of how much of the overall process has been completed as it makes its way to 100%


### Improve Clarity of the Numbers in the "Overview" and "Optimize Media Files" sections

- It often causes confusion for users that the numbers in the "Overview" section are based only on Image files only (excluding PDF, etc) while the numbers in the "Optimize Media Files" section are based on all media files.
- Users don't understand why the numbers don't match up sometimes
- Could change this so both display numbers for all media files so it's more consistent
- Could also change the "Overview" section so it shows number and percentage of all media files optimized, then display subcategories for specific types, like images, PDFs, etc

<br><br>
## Suggestions for the Online App

- Users with One Time quota not able to use the "Auto Convert PNG to JPEG" option. Should they be?
- Dynamically add year in footer so it stays up to date. Currently displays © WP MEDIA 2017


<br><br>
## Issue Where Multiple Invoices Generated
https://secure.helpscout.net/conversation/1281787405/194734 <br>
- For seemingly random reasons, sometimes accounts have many invoices generated in Facturation for the same charge
- Invoices can be created multiple times on different days
