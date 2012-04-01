When to sync
------------

Apps taking advantage of the Tweet Marker API for timeline syncing should think about what the best user experience is for their app. This generally means deciding between one of two approaches:

* Manual: Only sync to the server when the user explicitly requests it, such as when tapping on a tweet or clicking a button in your app. This approach may be useful for apps that have such a custom or complicated UI that they are not a perfect fit for how Tweet Marker works.
* Automatic: Hit the server when the app comes to the front and when it loses focus. Optionally, also poll the server at regular intervals while the app is running to see if the marker has changed. When the timeline has scrolled, wait a little while and if nothing else has changed, publish the marker back to the server.

Some combination of the above two approaches may also work for your app. Mobile apps should at a minimum sync on launch and on quit. Since the user is opening and closing apps often, this may be enough. Desktop and iPad apps should consider more actively polling and pushing synced data, as the user is likely to leave these apps running for some time.

If your app is regularly calling the API, please experiment with the best timing that produces a good experience but does not require too many requests. I recommend starting with no less than 3 minutes for a regular GET poll, and no less than 10 seconds for a delayed POST after scrolling.

User preferences
----------------

Tweet Marker should usually be disabled by default. If you'd like to encourage your customers to enable Tweet Marker, prompting on first launch is fine. Please contact support@riverfold.com if you think your app should always have Tweet Marker enabled.

Add a user preferences for your app that mentions Tweet Marker either in the title or value of the setting. If there is room in your settings screen, please also show the tweetmarker.net domain name or full URL so that customers can find out more about how syncing works.