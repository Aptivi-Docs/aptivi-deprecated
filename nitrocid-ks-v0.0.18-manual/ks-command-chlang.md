# chlang command

## Summary

Changes system language

## Description

The system language can be changed either by manually editing configuration files, using Kernel Simulator Configuration Tool, or by using this command. Restart is not required, since printing text, viewing user manual, and updating help list relies on "currentLang" field. It changes the value of "currentLang" field to the appropriate found language in the array of available languages.

Available languages:

* arb: Arabic transliterated language
* arb-T: Arabic translated language
* azr: Azerbaijan language
* ben: Bengali transliterated language
* ben-T: Bengali translated language
* chi: Chinese transliterated language
* chi-T: Chinese translated language
* cro: Croatian language
* ctl: Catalan language
* cze: Czech language
* dan: Danish language
* dtc: Dutch language
* eng: English language (default)
* fin: Finnish language
* flp: Filipino language
* fre: French language
* ger: German language
* ind: Hindi transliterated language
* ind-T: Hindi translated language
* ita: Italian language
* ndo: Indonesian language
* jpn: Japanese transliterated language
* jpn-T: Japanese translated language
* kor: Korean transliterated language
* kor-T: Korean translated language
* mal: Malay language
* mts: Maltest language
* nwg: Norwegian language
* pol: Polish language
* ptg: Portuguese language
* pun: Punjabi transliterated language
* pun-T: Punjabi translated language
* rmn: Romanian language
* rus: Russian transliterated language
* rus-T: Russian translated language
* slo: Slovak language
* som: Somali language
* spa: Spanish language
* srb: Serbian transliterated language
* srb-T: Serbian translated language
* swe: Swedish language
* uzb: Uzbek language
* vtn: Vietnamese language

## Command usage

* `chlang <language>`

## Examples

* `chlang fre`: Changes system language to French
