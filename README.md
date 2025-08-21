# Terbium Package Repo

The official Terbium Package repo

## Repo MetaData

MetaData for your repo is important for identifying that its a Terbium Package Repo. Right now there are only 2 configuration options but likely a few more will be added with time. 

- Name: `string` - The display name of the repo
- Icon: `string` - The icon of your repo (if left blank, defaults to tb.svg)

## Adding Apps

Adding Apps to the repo is fairly easy, in the repo under the `apps` array, you can add apps in one of the following formats. Also, for storing assets, images, etc its recommended to use the assets folder however hosting assets elsewhere is fine too

### Adding PWAs

A PWA (Progressive Web App) is essentially just a web application and they are fairly easy to setup. The wmArgs should be setup exactly how you would for any normal `.tbconfig` but with `proxy` set to `true`.

- Example
    ```json
    {
        "name": "YouTube",
        "icon": "https://raw.githubusercontent.com/TerbiumOS/app-repo/main/assets/com.tb.youtube/icon.png",
        "description": "Share your videos with friends, family, and the world.",
        "developer": "Google",
        "pkg-name": "youtube",
        "images": [
            "https://raw.githubusercontent.com/TerbiumOS/app-repo/main/assets/com.tb.youtube/images/1.png"
        ],
        "wmArgs": {
            "title": {
                "text": "YouTube",
                "weight": 600
            },
            "icon": "https://raw.githubusercontent.com/TerbiumOS/app-repo/main/assets/com.tb.youtube/icon.png",
            "src": "https://youtube.com",
            "size": {
                "width": 600,
                "height": 400
            },
            "single": true,
            "resizable": true,
        }
    }
    ```

### Adding TAPP's

If you have a packaged TAPP you **MUST** include a `pkg-download` instead of `wmArgs`. The other fields can continue being in TARF (Terbium App Repo Format)

- Example
    ```json
        {
            "name": "About Proxy",
            "icon": "https://aboutproxy.pages.dev/aboutbrowser/darkfavi.png",
            "description": "Chrome for your browser",
            "images": [
                "https://raw.githubusercontent.com/TerbiumOS/app-repo/main/assets/com.tb.youtube/images/1.png"
            ],
            "developer": "r58playz",
            "pkg-name": "aboutproxy",
            "pkg-download": "https://tbapps.pages.dev/assets/aboutproxy.TAPP.zip"
        },
    ```

### Adding Anura Apps

If you have a packaged TAPP you **MUST** include a `anura-pkg` instead of `wmArgs` or `pkg-download`. The other fields can continue being in TARF (Terbium App Repo Format)


- Example
    ```json
        {
            "name": "Snae Player",
            "icon": "https://raw.githubusercontent.com/MercuryWorkshop/anura-repo/master/apps/anura.music/icon.png",
            "description": "A music client ported to Anura",
            "developer": "Mercury Workshop",
            "pkg-name": "snaeplayer",
            "anura-pkg": "https://raw.githubusercontent.com/MercuryWorkshop/anura-repo/master/apps/anura.music/app.zip"
        }
    ```

## Adding Packages

As of August 2025, Package support is not implemented yet but it has been added as a option in the manifest.json for future use. Documentation will be provided when the time comes
