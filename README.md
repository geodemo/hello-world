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

If you already have some custom language parsing rules and don't want to loose them, just copy/paste the following blocks in your `FunctionListRules.xml`.

**PHP parsing rules**
```xml
    <Language name="PHP" imagelistpath="plugins\Config\php.bmp">
        <CommList param1="#" param2="" />
        <CommList param1="//" param2="" />
        <CommList param1="/\*" param2="\*/" />
        <Group name="INCLUDE" subgroup="" icon="2" child="2" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg='^\s*(include|require)(_once)?[\s&apos;&quot;\(]*' regexfunc="[\w./-]+" regexend='[&apos;&quot;\)\s]*;$' bodybegin="" bodyend="" sep="" />
            <Rules regexbeg="^\s*use\s+" regexfunc="[\w\\]+" regexend="[\w\s]*;$" bodybegin="" bodyend="" sep="" />
        </Group>
        <Group name="CLASS" subgroup="" icon="1" child="1" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="\{" keywords="">
            <Rules regexbeg="^\s*(abstract|final)?\s*class\s*" regexfunc="\w+" regexend="" bodybegin="\{" bodyend="\}" sep="" />
        </Group>
        <Group name="INTERFACE" subgroup="" icon="0" child="0" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="\{" keywords="">
            <Rules regexbeg="^\s*interface\s+" regexfunc="\w+" regexend="" bodybegin="\{" bodyend="\}" sep="" />
        </Group>
        <Group name="CONSTANT" subgroup="" icon="8" child="8" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*const\s+" regexfunc="[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
            <Rules regexbeg='^\s*define\s*[\(&apos;&quot;\)\s]+' regexfunc="[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
        </Group>
        <Group name="PUBLIC VAR" subgroup="" icon="6" child="6" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(public|var)\s+" regexfunc="\$[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
        </Group>
        <Group name="PUBLIC STATIC VAR" subgroup="" icon="7" child="7" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(public\s+)?static\s+(public\s+)?" regexfunc="\$[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
        </Group>
        <Group name="PROTECTED VAR" subgroup="" icon="4" child="4" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*protected\s+" regexfunc="\$[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
        </Group>
        <Group name="PROTECTED STATIC VAR" subgroup="" icon="5" child="5" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(protected\s+static|static\s+protected)\s+" regexfunc="\$[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
        </Group>
        <Group name="PRIVATE VAR" subgroup="" icon="9" child="9" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*private\s+" regexfunc="\$[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
        </Group>
        <Group name="PRIVATE STATIC VAR" subgroup="" icon="10" child="10" autoexp="0" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(private\s+static|static\s+private)\s+" regexfunc="\$[\w_]+" regexend="" bodybegin="" bodyend="$" sep="" />
        </Group>
        <Group name="CONSTRUCTOR" subgroup="" icon="21" child="21" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(public\s+)?function\s+" regexfunc="[__construct]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PUBLIC METHOD/FUNCTION" subgroup="" icon="19" child="19" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(public\s+)?function\s+" regexfunc="(?&lt;!\b__construct)\b(?!(?:__construct)\b)[\w_]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PUBLIC STATIC METHOD" subgroup="" icon="20" child="20" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(public\s+)*static\s+(public\s+|final\s+)*function\s+" regexfunc='[&quot;\w_]+\s*\(.*\)' regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PUBLIC ABSTRACT METHOD" subgroup="" icon="23" child="23" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(public\s+|static\s+)*abstract\s+(static\s+|public\s+)*?function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*;" bodybegin="" bodyend="" sep=";" />
        </Group>
        <Group name="PUBLIC FINAL METHOD" subgroup="" icon="22" child="22" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(public\s+)?final\s+(public\s+|static\s+)*function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PROTECTED METHOD" subgroup="" icon="11" child="11" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*protected\s+function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PROTECTED STATIC METHOD" subgroup="" icon="12" child="12" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(static\s+(final\s+)?protected\s+(final\s+)?|protected\s+static\s+(final\s+)?)function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PROTECTED ABSTRACT METHOD" subgroup="" icon="13" child="13" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(static\s+)?(abstract\s+(static\s+)?protected|protected\s+(static\s+)?abstract)\s+(static\s+)?function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*;" bodybegin="" bodyend="" sep=";" />
        </Group>
        <Group name="PROTECTED FINAL METHOD" subgroup="" icon="14" child="14" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*((protected\s+final\s+(static\s+)?)|final\s+(static\s+)?protected\s+(static\s+)?)function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PRIVATE METHOD" subgroup="" icon="16" child="16" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(final\s+)?private\s+(final\s+)?function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
        <Group name="PRIVATE STATIC METHOD" subgroup="" icon="17" child="17" autoexp="4" matchcase="0" fendtobbeg="" bbegtobend="" keywords="">
            <Rules regexbeg="^\s*(static\s+(final\s+)?private\s+(final\s+)?|private\s+static\s+(final\s+)?)function\s+" regexfunc="[\w_]+\s*\(.*\)" regexend="\s*" bodybegin="\{" bodyend="\}" sep=";" />
        </Group>
    </Language>
```

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