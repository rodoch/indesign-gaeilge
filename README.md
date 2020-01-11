# Irish-language hyphenation in Adobe InDesign

Updated: 11 January 2020

Hyphenation is the automated process of breaking words between lines to create more consistency across a text block. When text is justified—that is to say, when text is set to fill the full width of space available—hyphenation is essential to providing optimum legibility and avoiding 'rivers' or large, unattractive gaps running vertically through the text.

## Hyphenation in Irish-language texts

In the digital age, hyphenation has often been neglected in Irish-language printed text. Sometimes it turned off or, worse again, implemented according to English-language or 'language-neutral' orthography. Some publications avoid using justified text altogether; perhaps partly for the reason that doing so avoids having to tackle the hyphenation question.

Hyphenation, when done wrong, can be particularly off-putting for the reader: consider where a word like *comhairle* is hyphenated as 'com- hairle', with the segment 'hairle' beginning on a new line. This is extremely hard to parse for a competent reader of Irish as the letter 'm', in this case, is modified or lenited by the 'h', known as a *séimhiú*. Irish orthography dictates that these letters should never be separated and to do so would be comparable to representing the English-language word 'though' as 'thou- gh'. As such, *comhairle* is much better hyphenated as 'comh- airle'. These issues are discussed in greater detail in [an article](http://www.tug.org/TUGboat/Articles/tb24-2/tb77scannell.pdf) by language technologist Kevin Scannell.

## Software solutions for hyphenation

Adobe InDesign has been the industry-standard software for typesetting and laying out text for publication for some time now. InDesign comes prepackaged with spelling and hyphenation tools for a number of languages but Irish is not among these. This may go some way to explain the relative absence of proper hyphenation in Irish-language publications as practicioners may believe no technical solution is available.

Thankfully, this is not the case. Two factors mean that we can have proper hypenation for Irish:

1. InDesign provides facilities to [add additional Hunspell dictionaries](https://helpx.adobe.com/ie/indesign/kb/add_cs_dictionaries.html) (including hyphenation dictionaries, used for language-specific hyphenation) to those that come preinstalled with the program.
2. Thanks to the work of [Kevin Scannell](https://cadhan.com/fleiscin/) a comprehensive set of hyphenation rules for Irish is available.

While these solutions have been available for some time many people are unaware of how to put the pieces together and enable Irish-language hyphenation. The remainder of this document provides a step-by-step guide in the hopes that proper hyphenation can be more widely adopted.

## How to enable Irish-language hyphenation in Adobe InDesign

The steps below describe how to obtain to appropriate Irish-language dictionary and install it in InDesign on both Windows and Mac OS platforms. It takes a couple of clicks and an understanding of where files are stored on your computer, but no specialist technical knowledge is required. That said, it bears mentioning that a few commercial solutions, based on InDesign plugins, exist. These are somewhat simpler to install—usually requiring you to do no more than download a file and click OK a couple of times—but do not come for free. Some commerical options are discussed at the end of this document.

**Note:** If you are using Adobe InDesign Creative Cloud 2015 (or above) on Mac OS, please note you will *have to* use a commerical solution such as the one described at the end of this article. This is due to a long-standing bug that has been acknowledged by Adobe but which they seem in no hurry to fix. In this case, it is possible to add the additional dictionaries but they will be treated rather like a foreign virus by the OS. The problem is described in more detail [here](https://indesign.uservoice.com/forums/601180-adobe-indesign-bugs/suggestions/32569186-hunspell-dictionaries-cannot-be-added-in-sierra-or).

1. First, you will need the appropriate spelling and hyphenation dictionaries for Irish. For simplicity, you can download them [here](). I retrieved them from the Mozilla Firefox [language pack](https://addons.mozilla.org/en-US/firefox/addon/litreoir-gaelspell-do-mhozilla/) repository and, if you're reading this in this distant future, you might want to go there to get the latest version.
2. Unzip the file you just downloaded. (If you downloaded the package from Mozilla it will likely have a `.xpi` extension or similar but it's really just a standard archive file: you can rename the file extension to `.zip` and extract the files as normal.)
3. The resulting folder should contain at least the following three files: **ga_IE.aff** (an affix file), **ga_IE.dic** (the spelling dictionary), **hyph_ga_IE.dic** (the hyphenation dictionary). The naming of the files is important, it's part of how InDesign finds and recognises them. If, for any reason, your files look different see if you can rename them appropriately.
4. Create a new folder named **ga_IE** and place the files from the previous step there. InDesign stores all of its dictionary files in a particular place on your machine. In the next step we will move this folder there.
5. Move the **ga_IE** folder to one of the following locations (choose the location that matches your operating system). If you can't find the location below there is a more extensive list available [here](https://helpx.adobe.com/ie/indesign/kb/add_cs_dictionaries.html). On Mac OS, you will need to right-click on the `AdobeHunspellPlugin.bundle` package and select 'Show Contents' to access the `Contents` folder within.
    - **Windows:** `%ProgramFiles%\Adobe\Adobe InDesign CC (64 bit)\Plug-Ins\Dictionaries\LILO\Linguistics\Providers\Plugins2\AdobeHunspellPlugin\Dictionaries`
    - **Mac OS:** `/Applications/Adobe InDesign CC/Resources/Dictionaries/LILO/Linguistics/Providers/Plugins2/AdobeHunspellPlugin.bundle/Contents/SharedSupport/Dictionaries`
6. We've now installed the dictionary files but we need to tell InDesign that they exist. Find a file named **Info.plist** in one of the following locations:
    - **Windows:** `%ProgramFiles%\Adobe\Adobe InDesign CC (64 bit)\Plug-Ins\Dictionaries\LILO\Linguistics\Providers\Plugins2\AdobeHunspellPlugin`
    - **Mac OS:** `/Applications/Adobe InDesign CC/Resources/Dictionaries/LILO/Linguistics/Providers/Plugins2/AdobeHunspellPlugin.bundle/Contents/`
7. Open the **Info.plist** file in a text editor application such as Notepad, Notepad++, Visual Studio Code, etc. Note that there are three sections in this file; `SpellingService`, `UserDictionaryService` and `HyphenationService`. Under each 'heading' there is a list of language codes enclosed in tags, such as `<string>kn_IN</string>`. For each section you need to add `<string>ga_IE</string>` tags to the list. It doesn't matter where in the list you place the new tags.
8. Restart InDesign.

You should now have access to Irish-language hyphenation in InDesign. Make sure InDesign knows which language it's dealing with by either setting the language in a paragraph style or character style (see the **Advanced Character Formats** tab).

### Commerical alternatives

If you don't fancy completing the steps above, there are a number of commercial solutions available, such as [MindHyph](http://mindsteam.com/products/mindhyph/index.html). These are typically paid software packages and that you download and install like any other piece of software and they require you to do very little. [Sigurður Ármannsson](https://font.is/) has also produced package specially for Irish (having previously done the same for Icelandic and a number of other languages) and it should be available on his web shop soon.
