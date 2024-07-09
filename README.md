# espanso-bib-generator
Generates a bib entry from a matching regex using espanso

## Installation

1. Install Python on your machine. The scripts uses the systems Python interpreter, but no external libraries.
2. Install [Espanso](https://github.com/espanso/espanso)
3. Place the scripts in the corresponding %CONFIG% folder of espanso ([Documentation](https://espanso.org/docs/configuration/basics/))

## Usage
Just write `:cite:<your search>:` anywhere, it will spawn a GUI and then replace your text with the .bib entry you selected in the GUI. It uses the [DBLP](https://dblp.org/) API under the hood, which is restricted to computer science papers only. I highly recommend searching with `<Author> <Some parts of the title>` to improve the search results, as `<Some parts of the title>` often results in irrelevant results.

Note: Espanso limits the regex matches to 30 characters ([Source](https://github.com/espanso/espanso/security)), so you must limit your query.

## Config

- If you want to change the regex, edit [this line](https://github.com/Xeophon/espanso-bib-generator/blob/417d1a1a43f866afe680a54303fcc2cccf8b0910/espanso/match/bib_gen.yml#L11) to your preference.
- To increase the amount of results shown in the form, increase the limit in the API call in [this line](https://github.com/Xeophon/espanso-bib-generator/blob/417d1a1a43f866afe680a54303fcc2cccf8b0910/espanso/scripts/dblp_multi_search.py#L8)
- I added code to change the DBLP bibkeys to my liking. If you want to change it, edit [this function](https://github.com/Xeophon/espanso-bib-generator/blob/417d1a1a43f866afe680a54303fcc2cccf8b0910/espanso/scripts/bib_generator.py#L18)
