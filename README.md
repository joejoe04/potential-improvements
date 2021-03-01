# Suggestions to add to the Support Wishlist

https://github.com/wp-media/imagify/issues/898 - Allow to search users by name, surname, or partial email

https://github.com/wp-media/imagify/issues/714 - When scheduling a cancellation, quota is reset when it shouldn't

https://github.com/wp-media/imagify/issues/886 - Allow admins to increase available quota by any value

https://github.com/wp-media/imagify-plugin/issues/521 - Fix WebP Not Resizing Issue





<br><br>
# Suggestion for Subscription-related Issues
Lay out all credits, prorated charges, and the final amount user will be charged for upgrade/downgrade during the checkout process:

## Upgrades
- Credit amount for unused portion of former plan
- Prorated charge for remainder of billing period on new plan
- Actual amount will be charged for upgrade
- Normal payment going forward

## Downgrades
- Credit amount for unused portion of former plan
- Prorated charge for remainder of billing period on new plan
- Amount of credit left on account after accounting for the 2 above values
- Normal payment amount after credit used

## Could We Possibly Change How Updates Are Charged?
https://secure.helpscout.net/conversation/1426138959/239537/ <br>
https://wp-media.slack.com/archives/C7CTJKAA2/p1614062521002000
- When upgrading from monthly to yearly, the charge is made immediately
- But if upgrading from Growth monthly to Infinite monthly, the charge is not made immediately
- This causes confusion and frustration because users usually think the charge is being applied immediately, so when their next payment is larger than they expect, they don't understand why
- Also, if they happen to cancel that same month, they still end up getting charged for the upgrade at the end after they've unsubscribed and they get mad about the charge
- They may also delete their card or PayPal billing agreement in the meantime and then we end up not getting the money for the upgrade at all.

## Issue With Switching a User's Subscription to Annual Billing
- Stripe (think Braintree too) does not register the change via cron job from Imagify when you set "Is Monthly" to No
- It works if you're changing to a 'plan' 3 months, but not if only changing the "Is Monthly" option

## Cannot Switch PayPal Payments From Monthly to Yearyl or Vice Versa
- Is this fixable from our end in any way?
- Might involve process where making this change in Imagify profile does the following in Braintree:
    - Cancel current subscription
    - Create new subscription with new billing period (monthly or yearly) while charging only the amount for the upgrade minus the remaining value from previous plan

## Subscription Page Shows $69.93 Price for Infinite Yearly Plan With WPR30 Coupon, But Charges Them $84.92
https://secure.helpscout.net/conversation/1353317619/218627 <br>
https://secure.helpscout.net/conversation/1404252273/0/

## PayPal - Canceling Billing Agreement Also Cancels Imagify Subscription Immediately and Makes People Upset / Confused
https://secure.helpscout.net/conversation/1347879945/215851 <br>
https://secure.helpscout.net/conversation/1366196035/0/ <br>
https://secure.helpscout.net/conversation/1366196035/222892/ <br> 
https://secure.helpscout.net/conversation/1379065998/226638/ <br>
https://secure.helpscout.net/conversation/1378927409/226606/ 
- Could it be possible for this to schedule subscription to cancel instead, and then to also delete the payment method once the subscription gets canceled?
    - I know this change happened when PayPal Billing Agreement Cancellations were automated, so I know this may not be possible.
- If this isn't possible, we could at least add a warning to checkout page for PayPal asking users not to cancel their billing agreement or their subscriptions will be ended immediately

## Users Stuck With Darkened Overlay on Subscriptions Page
https://secure.helpscout.net/conversation/1364273307/0/?folderId=3985605 <br>
https://secure.helpscout.net/conversation/1362150680/221749?folderId=676697 

## Quota is Reset When Subscription Scheduled For Cancellation





<br><br>
# Marketing Issues Suggestions

## Emails Going Out Sometimes Say "Congratulations on Optimizing 0 Images" While Also Saying Users Are Out of Quota
https://secure.helpscout.net/conversation/1364725926/0/ <br>
https://secure.helpscout.net/conversation/1384503319/0/ <br>
https://secure.helpscout.net/conversation/1403868054/233515 

## INFINITE20 / UNLIMITED20 Coupons Not Working For Some People
https://secure.helpscout.net/conversation/1412414683/235880/ <br>
https://secure.helpscout.net/conversation/1392358874/230218/ <br>
https://secure.helpscout.net/conversation/1393963031/230663/ <br>
https://secure.helpscout.net/conversation/1394798488/230913/ 
- Often showing as expired or invalid






<br><br>
# General UI / UX and Other Options Suggestions

## Offer Better Optimization Error Messages
- Is there any way to prevent cURL error 28 errors or timeouts during optimization from giving the error message that users are out of credit?
    - It leads to them buying more quota when they don't need it, or getting frustrated that they just bought a plan and think they've already run out of quota.

## Confusing Display Issues When User Has Infinite Plan and Also One-Time Quota
https://secure.helpscout.net/conversation/1437476847/242752?folderId=3985605 <br>
https://secure.helpscout.net/conversation/1428722223/0/?folderId=676697 
- "You have nn% credit left" displayed based on how much one-time quota is left. 
    - Confuses users because they think they should be shown that they have unlimited quota
- "You have 0% credit left" displayed if sub-accounts granted more quota than amount of one-time quota user has
<img src="https://i.imgur.com/Tp0QfVi.png">
- Also, when this is the case, in the Bulk and Settings pages, you get the "You have 0% space credit left" banner

## Missing WebP Versions in the Settings Page
- When it lists NNN images with missing WebP versions, it would be very much helpful if it would also list which images it is referring to. 
- When users have 10s of thousands of images and this isn't working, it's very hard to offer them a good solution because there's no way to know which images it's referring to without searching manually through all images.

## Consider Adding Option to Specify Whether WebP Images Should Be Generated If They'll Be Larger Than Original Format
- Same as option #3 in https://wordpress.org/plugins/webp-express/
- Would be good for those using CDN/Cloudflare who also have image display issues with picture tag option
- Might even be worth considering having this option not check for WebP compatibility because sometime in the near future it may no longer be necessary with Safari finally starting to support WebP and I can see users wanting a function to just swap out all their image URLs to the WebP version so they don't need to manually change them for all their pages.

## Should we add "Not to be used with Cloudflare" warning by the "Use rewrite rules" option?





<br><br>
# Bulk Optimizer Page Suggestions

## Make the quota used / quota left guage more consistent across the App and the plugin

- Displays in the App as follows:
<img src="https://i.imgur.com/VhNgfuG.jpg">

- Displays in the plugin as follows:
<img src="https://i.imgur.com/UKQ31aA.jpg">

- Might be good to also display the 32.04 / 525MB used to make the experience more consistent

## Make it clear to users that when the Bulk Optimizer is run multiple times, images that are already optimized are not re-optimized

- Users often get the sense their quota is being wasted optimizing images that have already been optimzed when running Bulk Optimizer multiple times

- Could state somewhere on the Bulk Optimization page that images already optimized at current level will not be re-optimized if you run Bulk Optimizer multiple times

- I think the following may also contribute to this feeling from users. In this example, user has 8 images listed as already being optimized
<img src="https://i.imgur.com/1SSLMxl.jpg">

- But when you click "Imagif'em All" that number goes back down to 0, giving the impression that the 8 images may be being re-optimized
<img src="https://i.imgur.com/wcRIrw3.jpg">

- Instead, it may be better for this number to remain the same, and only increase if more images get optimized. The percentage could still start at 0% giving an indication of how much of the overall process has been completed as it makes its way to 100%

## Improve Clarity of the Numbers in the "Overview" and "Optimize Media Files" sections

- It often causes confusion for users that the numbers in the "Overview" section are based only on Image files only (excluding PDF, etc) while the numbers in the "Optimize Media Files" section are based on all media files.
- Users don't understand why the numbers don't match up sometimes
- Could change this so both display numbers for all media files so it's more consistent
- Could also change the "Overview" section so it shows number and percentage of all media files optimized, then display subcategories for specific types, like images, PDFs, etc

## One-time Plans Still Mentioned When Run Out of Credits in Bulk Optimizer and the Website Account Dropdown Menue
https://secure.helpscout.net/conversation/1397903954/231854?folderId=676697 <br>
https://secure.helpscout.net/conversation/1437812406/242889?folderId=676697

## IMAGIFY20 Coupon Code Banner Still Showing in Bulk Optimization Page





<br><br>
# Suggestions for Media Library Page

## Improve display of Optimization Info for Each Image
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

## When optimization is hanging in Media Library on images, would be nice to have a way to stop it
- Frustrating for users when it's just hanging on the "Optimizing..." for many minutes without a way for them to stop it
- Would also be nice for while we are testing different things to be able to stop optimization


<br><br>
## Suggestions for the Online App
- Dynamically add year in footer so it stays up to date. Currently displays © WP MEDIA 2017

