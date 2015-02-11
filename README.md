IJD Seminar 2015-03-03
==============

This repository contains the presentation about my work on the projects [PLM](https://github.com/oster/PLM) and [webPLM](https://github.com/MatthieuNICOLAS/webPLM). I will present it at the IJD seminar held the 2015-03-03.

Generating the presentation file
---------------

If you want to re-generate the presentation file, you need to install [pandoc](http://johnmacfarlane.net/pandoc/). Then run the following command in the repository: 
```
pandoc -t revealjs --css path/to/theme/theme.css --variable theme=theme -s slides.md -o slides.html
```
You can then  open the generated file in a browser.

Tips
---------------

You may want to create a function to easily generate the slides like the following one:

```
function mdToReveal () {
  if [ -z "$1" ]; then
    echo "Usage: mdToReveal [theme] filename";
  else
    name=$1
    theme="simple"
    if [ ! -z "$2" ]; then
      name=$2
      theme=$1
    fi
    pandoc -t revealjs --css reveal.js/css/theme/$theme.css --variable theme=$theme -s $name.md -o $name.html
    echo "Generated $name.html" 
  fi
}
```