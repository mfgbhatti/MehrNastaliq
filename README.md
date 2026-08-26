# Mehr Nastaliq — Discourse Theme Component

A Discourse theme component that adds **Mehr Nastaliq** as the primary font for your Discourse community.

The component is designed especially for Urdu communities and provides an elegant Nastaliq reading experience while making adjustments to font size, line height, headings, and other interface elements to accommodate Nastaliq typography.

## Features

* Adds **Mehr Nastaliq** as the primary Discourse font.
* Includes both TrueType (`.ttf`) and Web Open Font Format 2 (`.woff2`) versions of the font.
* Uses the WOFF2 font for web rendering.
* Applies the font to both regular text and headings.
* Increases the base font size to improve Urdu readability.
* Provides increased line heights suitable for Nastaliq text.
* Enables normal font ligatures and font feature settings.
* Adjusts the Discourse header height for the Nastaliq font.
* Adjusts topic-link positioning where necessary for better Nastaliq rendering.
* Does not depend on an external font CDN.

## Installation

In your Discourse administrator interface:

1. Go to **Customize → Themes**.

2. Create or open the theme where you want to use this component.

3. Add a new theme component.

4. Select **Install via Git repository**.

5. Enter:

   `https://github.com/mfgbhatti/MehrNastaliq.git`

   6. Install the component.

   7. Add the component to your active theme.

   After installation, rebuild the theme if necessary and reload your Discourse site.

   ## Font Files

   The component includes two versions of the Mehr Nastaliq font:

   | Font file            | Format   | Purpose                                  |
   | -------------------- | -------- | ---------------------------------------- |
   | `MehrNastaliq.ttf`   | TrueType | Desktop/TrueType font asset              |
   | `MehrNastaliq.woff2` | WOFF2    | Web font used by the Discourse component |

   The font assets are declared in `about.json` and exposed to the theme's SCSS as `MehrNastaliqTrue` and `MehrNastaliqWeb`.

   The WOFF2 version is used as the primary web font:

   `MehrNastaliqWeb, Arial, sans-serif`

   ## Typography

   Mehr Nastaliq is intended primarily for Urdu and other scripts or languages that benefit from Nastaliq typography.

   The component sets the Discourse font and heading font to Mehr Nastaliq:

   ```css
   --font-family: MehrNastaliqWeb, Arial, sans-serif;
   --heading-font-family: MehrNastaliqWeb, Arial, sans-serif;
   ```

   It also increases the base font size to `1.125em` and uses larger line heights to give Nastaliq text enough vertical space.

   ### Line Heights

   | Setting |  Value | Purpose                  |
   | ------- | -----: | ------------------------ |
   | Small   | `1.75` | Compact text             |
   | Medium  |  `1.9` | Headings and larger text |
   | Large   |  `2.2` | Normal and smaller text  |

   These values are intended to improve the readability and visual spacing of Nastaliq text within the Discourse interface.

   ## How It Works

   The component registers both font formats using CSS `@font-face`:

   ```css
   @font-face {
         font-family: MehrNastaliqTrue;
             src: url($MehrNastaliqTrue) format("truetype");
   }

   @font-face {
         font-family: MehrNastaliqWeb;
             src: url($MehrNastaliqWeb) format("woff2");
   }
   ```

   The WOFF2 version is then assigned to Discourse's global font variables.

   The component also enables normal font ligatures and font feature settings for the document and headings, which is particularly useful for complex Urdu typography.

   ## Files

   ```text
   MehrNastaliq/
   ├── assets/
   │   ├── MehrNastaliq.ttf
   │   └── MehrNastaliq.woff2
   ├── common/
   │   └── common.scss
   ├── about.json
   ├── LICENSE
   └── README.md
   ```

   The exact font asset names are defined in `about.json`.

   ## License

   This repository contains the Discourse theme component code and the Mehr Nastaliq font assets under their respective licenses.

   The repository's theme component code is licensed under the **MIT License**. Please see [`LICENSE`](LICENSE) for the complete license text.

   If you redistribute or modify the included font files, please retain the original font licensing and attribution information supplied with the font.

   ## Credits

   * **Mehr Nastaliq** — Urdu Nastaliq typeface

   ## Repository

   Source code and updates:
    ```bash
    https://github.com/mfgbhatti/MehrNastaliq
    ```

   ## Contributing

   Issues, suggestions, and pull requests are welcome.

   If you find a problem with the font rendering, Urdu text layout, or compatibility with a newer Discourse version, please open an issue in the repository.

   ## Disclaimer

   This project is an independent Discourse theme component and is not affiliated with or endorsed by Discourse or the original creators of the Mehr Nastaliq font.

