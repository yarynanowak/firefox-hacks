# Firefox: hacks, tweaks, and productivity enhancements

Below are some of our favorite Firefox hacks, tweaks, and productivity enhancements that can be done via [Configuration Editor](https://support.mozilla.org/en-US/kb/about-config-editor-firefox) (about:config page) and by installing third-party extensions (add-ons for Firefox).

* [Security](#security)
* [Privacy](#privacy)
* [Telemetry](#telemetry)
* [DOM](#dom)
* [UI](#ui)
* [ICC color correction](#icc-color-correction)
* [Extensions (Add-ons for Firefox)](#extensions-add-ons-for-firefox)

## Security

#### Disable WebRTC

`media.peerconnection.enabled` => `false`

#### Fingerprinting

Firefox already has an Enhanced Tracking Protection feature that blocks a list of known "fingerprinters" when your privacy settings are set to Standard (the default) or Strict, whereas [Fingerprinting Protection](https://support.mozilla.org/en-US/kb/firefox-protection-against-fingerprinting) is a different, experimental feature under heavy development in Firefox.

`privacy.resistFingerprinting` => `true`

`privacy.trackingprotection.fingerprinting.enabled` => `true`

#### Punycode

Enable IDN [Punycode](https://kb.mozillazine.org/Network.IDN_show_punycode) (display the "raw", punycode version of internationalized domain names).

`network.IDN_show_punycode` => `true`

## Privacy

#### Firefox containers

Enable Container Tabs and its UI setting. [Firefox containers](https://support.mozilla.org/en-US/kb/how-use-firefox-containers) let you separate your browsing activities into color-coded tabs for banking, work and personal browsing. This allows you to always open new tabs in containers of your choosing for a more private browsing experience. Each container is isolated from the others, so you can access sites logged into different accounts.

`privacy.userContext.enabled` => `true`

`privacy.userContext.ui.enabled` => `true`

`privacy.userContext.newTabContainerOnLeftClick.enabled` => `true`

#### Geolocation

Disable Geolocation Tracking.

`geo.enabled` => `false`

#### Widevine

Disables the Widevine Content Decryption Module provided by Google.

`media.gmp-widevinecdm.enabled` => `false`

#### Pocket

Disable Pocket integration.

`extensions.pocket.enabled` => `false`

## Telemetry

This is the data submission master [kill switch](https://firefox-source-docs.mozilla.org/toolkit/components/telemetry/internals/preferences.html) (if disabled, no policy is shown or upload takes place).

`datareporting.policy.dataSubmissionEnabled` => `false`

Disable recommendations in about:addons' Extensions and Themes panes.

`extensions.htmlaboutaddons.recommendations.enabled` => `false`

## DOM

#### Context menu

Web pages won't be allowed to manipulate or block the context menu.

`dom.event.contextmenu.enabled` => `false`

#### Resizing windows

Prevent scripts from moving and resizing open windows.

`dom.disable_window_move_resize` => `false`

## UI

#### Compact Density

For anyone wishing to maximize the amount of space available for web content in their browser, Firefox offers a useful "Compact density" option, which reduces the size of the user interface. However, starting with Firefox 89, this option is hidden by default. The following settings will help you get this option back.

`browser.compactmode.show` => `true`

Next step: More tools -> Customize toolbar... -> Density -> Compact (not supported).

#### Bookmarks

Open bookmarks in a new tab (rather than existing window).

`browser.tabs.loadBookmarksInTabs` => `true`

#### Closing last tab

Prevent Firefox from exiting when you close the last tab.

`browser.tabs.closeWindowWithLastTab` => `false`

#### View Source

This preference controls whether lines in View Source that are too long to fit the window will wrap to the next line or cause a horizontal scroll bar.

`view_source.wrap_long_lines` => `true`

## ICC color correction

Color management allows images and colors to be displayed consistently across a variety of devices. [Firefox recognizes](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/3.5/ICC_color_correction_in_Firefox) embedded ICC profiles in image files and uses a local color profile to perform the color adjustments.

Color correction can be controlled by setting the value of the `gfx.color_management.mode` preference, as follows:

`0` -> Disable color management

`1` -> Enable color management for rendered graphics

`2` -> Enable color management for tagged graphics only (Default)

Full color management means that everything rendered by Firefox, with the exception of plugins, has its colors corrected.

## Extensions (Add-ons for Firefox)

#### uBlock Origin

[uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) (uBO) is a free and open-source browser extension for content filtering, including ad blocking. Out of the box, uBO blocks ads, trackers, coin miners, popups, etc.

#### Facebook Container

[Facebook Container](https://addons.mozilla.org/en-US/firefox/addon/facebook-container/) works by isolating your Facebook identity into a separate container that makes it harder for Facebook to track your visits to other websites with third-party cookies.

#### DuckDuckGo Privacy Essentials

[DuckDuckGo Privacy Essentials](https://addons.mozilla.org/en-US/firefox/addon/duckduckgo-for-firefox/) provides simple and seamless privacy protection for your browser: tracker blocking, cookie protection, DuckDuckGo private search, email protection, HTTPS upgrading, and much more.

#### SingleFile

[SingleFile](https://addons.mozilla.org/en-US/firefox/addon/single-file/) is an add-on for Firefox Desktop and Mobile that helps you to save an entire webpage including images, styling, frames, fonts etc. as a single HTML file.
