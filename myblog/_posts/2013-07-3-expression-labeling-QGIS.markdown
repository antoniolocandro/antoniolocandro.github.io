---
layout: post
title: expression labelling QGIS
date: {}
categories: python
published: true
---

[QGIS][qgis_link] is a very nice GIS open source software that I have been playing a lot lately. I think it is getting really good specially the new development version QGIS 2.0. Everyday I use [ARCGIS] [esri] Advanced 10.0 at work and when I switch to fool around with QGIS I try to do some things that I would normally do with ARCGIS.

One of those things is **expression labelling**, it´s one of those features that I use a lot at work and wanted to try out with QGIS 2.0 aka **QGIS-master**. 

Using Expression Labeling:

1. Select the layer you want to label
2. Right click on the layer and select properties, now the property dialog will open
3. Select from the **left option** labels; please make the world a favour and don't use deprecated labels (for some reason QGIS developers chose to keep them when someone upgrades from QGIS 1.8 to QGIS 2.0. Honestly it would be better to just eliminate that since this will only make the support for old labeling for ever
4. tick the option label this layer with the epsilon symbol &epsilon: a new dialog window will open with lots of options but for this blog post lets just use **fields and values**
5. if you expand the available options **fields and values** you will see the fields and attributes your data has for this blog post the sample layer has 4 fields


|   fields  |
|: ------- :|
|latitude   |
|longitude  |
|x          |
|y          |

Now some examples!

**Adding just one field**

double click on the field you want to use, lets say `longitude` 

Now the expression will look 

```
     "longitude" 
```

**Concatenating two fields**

double click on the first field, then add `||`(you can either use your keyboard or double click the symbol on the expression dialog) then double click con the second field you want to add

Now the expression will look

```
	 "longitude"  ||  "latitude" 
```
	 
**Having two fields each on a different line**

repeat the steps before but now you will add '\n' after the first `||` and then add `||`

Now the expression will look

```
     "longitude"  ||+'\n'||  "latitude" 
 ```
 
**Adding some explanatory text now**

repeat the steps before but now add the text inside single quotes `'`

Now the expression will look
 
```
    'longitude ' ||  "longitude"  || '\n' ||'latitude ' ||   "latitude" 
```

![screenshot](/assets/QGIS/expression-labelling-QGIS-4.jpg)

***
**In summary**

`||` concatenates 

`'\n'` equals a new line

`"Longitude"` will return the values in the Longitude field, notice the double quotes

`'Longitude'` will just return the string Longitude, notice the single quotes

***
 
[esri]: http://esri.com
[qgis_link]:    http://www.qgis.org
[twitter_richard]:    https://twitter.com/richardburcher
[code_academy]:    http://www.codecademy.com/
[python_link]:   http://www.python.org/