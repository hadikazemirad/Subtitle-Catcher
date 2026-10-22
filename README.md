Subtitle Catcher
Subtitle Catcher is a Firefox extension for finding downloadable subtitles and media-related resources on web pages. It provides an English/Persian interface and includes subtitle conversion utilities.
Version: 2.1.14

Features
- Detects subtitle tracks and likely subtitle resources on the current page.
- Recognizes common subtitle formats, including VTT, SRT, ASS/SSA, SUB, TTML/DFXP, SBV, LRC, and other formats listed by the extension.
- Checks candidate subtitle responses before listing them, helping avoid false positives from URLs that merely look like subtitles.
- Attempts to associate subtitles with the video currently playing by comparing filenames when available.
- Detects video sources such as MP4, WebM, MKV, and HLS/M3U8, plus audio sources and video posters.
- Finds web-font resources, including fonts referenced by CSS @font-face.
- Converts WebVTT (.vtt) subtitles to SubRip (.srt) locally.
- Converts WOFF 1.0 fonts to TTF/OTF when supported by the browser. WOFF2 is retained in its original format because this build does not decode WOFF2.
- Supports English and Persian (Farsi) UI.
Detection depends on how a website serves its media. Protected, encrypted, DRM-based, or inaccessible resources may not be detected or downloadable. The extension does not promise to extract every stream from every website.
Installation in Firefox
1. Regular Firefox installation (recommended for everyday use)
For a permanent installation in standard Firefox, the extension must be signed by Mozilla.
1. Open the extension's Mozilla Add-ons page, once it has been published:
   Subtitle Catcher on Firefox Add-ons
2. Choose Add to Firefox.
3. Review the requested permissions and select Add.
4. Use the extensions button in the Firefox toolbar to open Subtitle Catcher. Pin it to the toolbar if desired.
Important: An .xpi file being named AMO_READY does not mean it is Mozilla-signed. A locally built or unsigned XPI generally cannot be installed permanently in normal Firefox. To distribute a permanent build, submit it to Mozilla Add-ons and use the signed XPI Mozilla provides. The link above is the general Add-ons site, not a listing for this extension.
2. Temporary installation (for testing)
Temporary installation is useful for testing a local XPI. Firefox removes the temporary add-on when Firefox closes or restarts.
1. Open Firefox.
2. Enter about:debugging in the address bar and press Enter.
3. Select This Firefox in the left sidebar.
4. Click Load Temporary Add-on….
5. Select Subtitle_Catcher_v2.1.14_AMO_READY(1).xpi from your computer. If Firefox does not accept the XPI, extract it and select the extension's manifest.json file instead.
6. Open a page containing an online video, then click the Subtitle Catcher toolbar icon.
To test a changed build, return to about:debugging and load the updated add-on again.
How to use
1. Open a website with a video or audio player.
2. Start or load the media if the site only reveals its sources after playback begins.
3. Click the Subtitle Catcher toolbar icon.
4. Review the resources the extension found. Available actions depend on the resource type.
5. For subtitles, choose the desired subtitle download or conversion action shown in the popup.
6. Change the popup language between English and فارسی using the language selector.
Some websites load media dynamically. If a resource is not listed, try starting playback and opening the popup again.
Permissions
The extension declares these Firefox permissions:
- activeTab — access related to the active tab when the user interacts with the extension.
- downloads — download resources selected by the user.
- <all_urls> host access — allow the content script and resource checks to work across websites.
The content script examines media elements, subtitle tracks, page links, CSS font references, and certain resource URLs on pages where it runs. Candidate subtitle resources may be fetched to verify that they contain subtitle data. Website login/session state may be used for these requests through the browser's normal credentials handling.

Only install the extension if you are comfortable with these permissions. Avoid downloading copyrighted material without authorization and follow each website's terms.
Privacy
The manifest declares no required data collection for Mozilla's add-on review metadata. This is not a guarantee that every website interaction is private: the extension checks resources on the pages you visit and may request candidate subtitle files from those sites. This project documentation does not claim that the extension has undergone an independent security audit.
Compatibility
- Firefox 109.0 or newer, as specified by the extension manifest.
- Websites that expose subtitle or media resources in a form the extension can inspect.
- WOFF 1.0 conversion requires browser support for DecompressionStream; if unavailable, conversion may not work.
- WOFF2-to-TTF conversion is not supported in this build.
Project contents
- manifest.json — extension metadata, permissions, and Firefox settings.
- content.js — scans the page for subtitle and media resource candidates.
- popup.html / popup.js — toolbar popup and its actions.
- README.md — project documentation.
Troubleshooting
- No results appear: Start the video, wait for the page to load its resources, and open the popup again. Some sites hide or protect their media URLs.
- A subtitle does not download: The website may require access the extension cannot use, the URL may have expired, or the server may block the request.
- Temporary installation disappears: This is expected after Firefox closes or restarts. Load the XPI again through about:debugging.
- Firefox refuses permanent installation: Use a Mozilla-signed XPI for normal Firefox, or use temporary installation for local testing.
License
No license is specified in this package. Add a LICENSE file before publishing if you want to grant others explicit permission to use, modify, and redistribute the project.
