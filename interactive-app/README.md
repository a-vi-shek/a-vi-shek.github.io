# HRI Task App: live demo

A working demo of the HRI Task App, a mobile web app that lets a construction worker receive, check, run and complete tasks assigned by a robot system.

This folder is a complete static website: open `index.html` through any web server, or publish it with GitHub Pages. The robot connection is **simulated**: use the round **DEV** button to play the robot and send tasks.

## Publish on GitHub Pages (username.github.io)

1. Open your `username.github.io` repository on GitHub.
2. Upload the files, either way works:
   - **As a folder:** upload `interactive-app/` itself. The demo lives at `https://username.github.io/interactive-app/`
   - **At the root:** upload the *contents* of this folder. The demo lives at `https://username.github.io/`
3. Make sure **Settings → Pages → Build and deployment** is set to *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. Wait a minute or two for the green check on the latest commit, then open the address.

To upload in the browser: in the repository click **Add file → Upload files**, drag the folder (or its contents) in, and commit. Upload everything, including the `assets/` folder, `sw.js`, `manifest.webmanifest` and the hidden `.nojekyll` file.

## Try it

1. Log in with a sample worker. The list is shown on the login screen:

   | Name | Password | Role |
   |---|---|---|
   | Hercule Poirot | `password1` | Masonry |
   | Sherlock Holmes | `password2` | Carpentry |
   | Jacques Clouseau | `password3` | Robot Operator |
   | Miss Marple | `password4` | Crane Operator |

   Or tap **Register** to create your own worker.
2. Check the profile and tap **Save & continue**.
3. Tap **DEV** (bottom right) → **Simulate incoming task**. Pick one marked *suitable* or *warns*.
4. Accept → Pause → Resume → Complete, and read the summary.

These are demo accounts only. Never reuse a real password here.

Best viewed on a phone, or in a desktop browser's phone view (`F12`, then `Ctrl+Shift+M`).

## Good to know

- **Data stays in the visitor's browser** (`localStorage`). Nothing is sent to a server, and each visitor gets their own copy of the sample workers.
- **Installable:** on Android Chrome, use *Add to home screen* / *Install app*. GitHub Pages serves over HTTPS, so this works.
- **No real robot connection.** Tasks come from the DEV panel. The app shows "Simulated link" to make this clear.

## Updating the demo

This folder is generated. Don't edit the files in it by hand. In the app's source project run:

```bash
npm run build:demo
```

Then upload the new `interactive-app/` contents over the old ones. Delete the old `assets/index-*.js` and `.css` files: the new build uses new file names.

The app caches itself for offline use, so returning visitors get the new version on their **second** visit after an update (or after one refresh).
