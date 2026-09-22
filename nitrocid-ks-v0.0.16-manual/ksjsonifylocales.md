# KSJsonifyLocales

KSJsonifyLocales is the new tool that can convert the language files consisting of translations of strings to a readable JSON format. It is to ensure that there are no misses in lines of one of the languages.

## How it works

KSJsonifyLocales contains the Translations folder that has the translation text files inside. When this program is run, it reads the entire folder, parses all the files, and converts them to the JSON output, which can be found in Translations/Done folder in the same place as the executable.

If built with COPYTOKS, it will copy the results directly to Kernel Simulator's resources, but it is untested, so use at your own risk.

To illustrate this, KSJsonifyLocales will:

* read the Translations folder,
* parse each language file,
* add them to the list of language files,
* read both the English and the target language lines,
* save them to JSON, and
* save them to Translations/Done or (optionally) ../Resources, assuming that the executable is found one level above the Kernel Simulator source folder

## How to use

* On Windows, you can just double-click on the KSJsonifyLocales.exe file. It's usually found on the same directory as Kernel Simulator.
* On Linux, you can run `mono KSJsonifyLocales.exe`
