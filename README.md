PHP5/CSS parsing rules for Function List plugin
===============================================

Language parsing rules patch (PHP5/CSS) for Function List plugin.

This will make Function List looks like a great code explorer such as the Eclipse Outline View ! [See screenshot here](http://www.geoffray.be/blog/php/patch-php5-pour-npp-function-list)

Note: version 1.0 only works since **Notepad++ 6.x** !

Installation
------------

- if necessary [download](http://sourceforge.net/projects/npp-plugins/files/Function%20List/) and install Function List 2.1
- close Notepad++
- unpack `FunctionListRules.xml` and `php.bmp` into your Notepad++'s `plugins\Config` folder

Contact
-------

[Geoffray Warnants](http://www.geoffray.be), send greetings [here](http://www.geoffray.be/blog/php/patch-php5-pour-npp-function-list) :)

ChangeLog
---------

- **v1.0**
    - new: public constructor recognition
    - fix: better methods recognition
    - fix: optimized icons file size
    - now using PCRE regular expressions (require Notepad++ 6.x)

- **v0.9.1** - 2012-04-17
    - new: added CSS language parsing rules
    - fix: fixed properties parsing rules since Notepad++ 6.x
    - fix: some minor improvements

- **v0.9** - 2010-12-11
    - initial release