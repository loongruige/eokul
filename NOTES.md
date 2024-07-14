## Sign-in system
With a recent update, now you log in to e-Okul VBS using a parent's e-Devlet account. Here's the idea: let's redirect the e-Devlet login page to a fake e-Okul VBS landing page that contains the user token (now realising, this is very insecure because in case of a mitm attach for whever reason, this might be exploited)

Sadly, we will have to do this through app patching, so only redirecting the base traffic to our custom localhost WON'T be enough, we will also have to handle the e-Devlet traffic. 

## Pictures
With a recent update, there was a vulnerability with the student picture system. The student pictures are still visible through the website, but I'm guessing another method of getting images were used for the mobile app. However, this wasn't pushed with a new app update, but most likely the route that points to the student picture simply returns a 404, so we probably won't have to do a work-around for it

### In case this doesn't work
Then, I probably will plan to patch 2 different versions of the app, one being the older version which probably will support student pictures, and one for the latest version

## App distribution
I am not planning to distribute patched apps (APK files) but rather an app to patch the base app, with a different signature and a different package name to minimise the conflict with the original app. In this patcher app, it is planned for the user will have the option to enter a custom server URL if they wish so.
