# Readme.md

![](https://github.com/melbsyd/Data_Analytics/blob/main/Agricultural_Census.png?raw=true)




**Table of Contents**

[TOCM]

[TOC]

# Purpose
This project is divided into **two parts**. **Part 1** "Agriculture Performance" deals with data manipulation regarding US agriculture indicators and then predicting farm value based on several variables that we choose. **Part 2** "US Elections", we will try to answer the question: ,,How does Democrat's election results affect farm performance?".

# Part 1 - Agriculture Performance
## Purpose
In Part 1, we will:

**1.** Compile the panel data set for every county (FIPS) and year (1928-1972)

**2.** Choose several variables which may be related to farm performance.
## Input Data (+ source)
* The "**United States Agriculture Data**" for the years **1840 - 2010** were published in Michigan by the ***Inter-university Consortium for Political and Social Research***.
The data used were obtained internally under confident measures, however, a modified version of this data colletion, which includes also the year 2012, is freely available on the webpage of the *Inter-university Consortium for Political and Social Research* under [this link](https://www.icpsr.umich.edu/web/ICPSR/studies/35206 "this link").

* The **State to FIPS** csv file may be used later in this document for converting the FIPS codes into the county names under these codes.

## Variables included
1. FIPS &#8594; *(smallest geographic unit)*
2. year &#8594; *(1928-1972)*
3. state &#8594; *(US states)*
4. pop &#8594; *(total population)*
5. area &#8594; *(total area)*
6. avgtotvalueperfarm &#8594; *(**"Average total value of a farm"** Constructed as follows: (value of the concrete farm + the value of its lifestock) / number of farms in that county)*
7.  It is created by dividing the Total Value of a farm by the number of farms in a county. 
The Total Value of a farm consists of the Value of the Farm + the Value of Lifestock, if that is separately listed.

## Code Walkthrough (step by step - only some parts selected for length purposes)
### Install & Load Packages 
Install and the following packages: `data.table()`, `haven()`, `dplyr()`, `tidyr()`, `readxl()`, `ggplot2()`, `plm()`, `stringr()`, `MAP()`, `purrr()`.

* `install.packages("data.table")`

* `library(data.table)`

### Load Agriculture Data (1925-1972)
Load agriculture data from years 1925-1972. The exact location of the files must be adjusted: *read_dta("...)*
* `data1925_1 <- read_dta("/Users/tomasnovak/Desktop/Agriculture/DataForWeek1/ICPSR_35206/DS0012/35206-0012-Data.dta")`

`.`

`.`

`.`

For some years are two data files, as for example for the year 1954. This is because the year 1954 does not contain a column FIPS, which serves as an identification code. Later in the code, we will extract the missing columns and join both data frames so each year contains the FIPS column.

### Load "State to FIPS" csv file
Load state to fips csv file. The exact location of the file must be adjusted: *read_excel("...")*
state_to_fips <- read_excel("StateFIPSicsprAB.xls")

### Check the Data Structure
To get a better sense of what the loaded agriculture datafiles look like, we will choose one of the data files and call function `str()`, as `str(data1925_1)`.

### Add column "Year"
Add a new column year to the loaded agriculture data frames following this syntax: `data1925_1 <- cbind(YEAR = 1925, data1925_1)`. Later on, we will use this new column Year in our regression as a unit-fixed effect.

### Extract the County Level Data
Following `data1925_1 <- subset(data1925_1, LEVEL == 1)` leaves in the agriculture dataframes only county level data. State and USA level data are dropped out.

### Rename Columns









## Final Data Summary Statistics
1. we have xx,xxx observsations
2. this is a list of variables and a description and summary for each



# Part 2 - US Elections
## Input Data (+ source)

## Variables included

## Code Walkthrough (step by step)

## Final Data Summary Statistics
1. we have xx,xxx observsations
2. this is a list of variables and a description and summary for each



###H3 header
####H4 header
#####H5 header
######H6 header
#Heading 1 link [Heading link](https://github.com/pandao/editor.md "Heading link")
##Heading 2 link [Heading link](https://github.com/pandao/editor.md "Heading link")
###Heading 3 link [Heading link](https://github.com/pandao/editor.md "Heading link")
####Heading 4 link [Heading link](https://github.com/pandao/editor.md "Heading link") Heading link [Heading link](https://github.com/pandao/editor.md "Heading link")
#####Heading 5 link [Heading link](https://github.com/pandao/editor.md "Heading link")
######Heading 6 link [Heading link](https://github.com/pandao/editor.md "Heading link")

##Headers (Underline)

H1 Header (Underline)
=============

H2 Header (Underline)
-------------

###Characters
                
----

~~Strikethrough~~ <s>Strikethrough (when enable html tag decode.)</s>
*Italic*      _Italic_
**Emphasis**  __Emphasis__
***Emphasis Italic*** ___Emphasis Italic___

Superscript: X<sub>2</sub>，Subscript: O<sup>2</sup>

**Abbreviation(link HTML abbr tag)**

The <abbr title="Hyper Text Markup Language">HTML</abbr> specification is maintained by the <abbr title="World Wide Web Consortium">W3C</abbr>.

###Blockquotes

> Blockquotes

Paragraphs and Line Breaks
                    
> "Blockquotes Blockquotes", [Link](http://localhost/)。

###Links

[Links](http://localhost/)

[Links with title](http://localhost/ "link title")

`<link>` : <https://github.com>

[Reference link][id/name] 

[id/name]: http://link-url/

GFM a-tail link @pandao

###Code Blocks (multi-language) & highlighting

####Inline code

`$ npm install marked`

####Code Blocks (Indented style)

Indented 4 spaces, like `<pre>` (Preformatted Text).

    <?php
        echo "Hello world!";
    ?>
    
Code Blocks (Preformatted text):

    | First Header  | Second Header |
    | ------------- | ------------- |
    | Content Cell  | Content Cell  |
    | Content Cell  | Content Cell  |

####Javascript　

```javascript
function test(){
	console.log("Hello world!");
}
 
(function(){
    var box = function(){
        return box.fn.init();
    };

    box.prototype = box.fn = {
        init : function(){
            console.log('box.init()');

			return this;
        },

		add : function(str){
			alert("add", str);

			return this;
		},

		remove : function(str){
			alert("remove", str);

			return this;
		}
    };
    
    box.fn.init.prototype = box.fn;
    
    window.box =box;
})();

var testBox = box();
testBox.add("jQuery").remove("jQuery");
```

####HTML code

```html
<!DOCTYPE html>
<html>
    <head>
        <mate charest="utf-8" />
        <title>Hello world!</title>
    </head>
    <body>
        <h1>Hello world!</h1>
    </body>
</html>
```

###Images

Image:

![](https://pandao.github.io/editor.md/examples/images/4.jpg)

> Follow your heart.

![](https://pandao.github.io/editor.md/examples/images/8.jpg)

> 图为：厦门白城沙滩 Xiamen

图片加链接 (Image + Link)：

[![](https://pandao.github.io/editor.md/examples/images/7.jpg)](https://pandao.github.io/editor.md/examples/images/7.jpg "李健首张专辑《似水流年》封面")

> 图为：李健首张专辑《似水流年》封面
                
----

###Lists

####Unordered list (-)

- Item A
- Item B
- Item C
     
####Unordered list (*)

* Item A
* Item B
* Item C

####Unordered list (plus sign and nested)
                
+ Item A
+ Item B
    + Item B 1
    + Item B 2
    + Item B 3
+ Item C
    * Item C 1
    * Item C 2
    * Item C 3

####Ordered list
                
1. Item A
2. Item B
3. Item C
                
----
                    
###Tables
                    
First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell 

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

| Function name | Description                    |
| ------------- | ------------------------------ |
| `help()`      | Display the help window.       |
| `destroy()`   | **Destroy your computer!**     |

| Item      | Value |
| --------- | -----:|
| Computer  | $1600 |
| Phone     |   $12 |
| Pipe      |    $1 |

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
                
----

####HTML entities

&copy; &  &uml; &trade; &iexcl; &pound;
&amp; &lt; &gt; &yen; &euro; &reg; &plusmn; &para; &sect; &brvbar; &macr; &laquo; &middot; 

X&sup2; Y&sup3; &frac34; &frac14;  &times;  &divide;   &raquo;

18&ordm;C  &quot;  &apos;

##Escaping for Special Characters

\*literal asterisks\*

##Markdown extras

###GFM task list

- [x] GFM task list 1
- [x] GFM task list 2
- [ ] GFM task list 3
    - [ ] GFM task list 3-1
    - [ ] GFM task list 3-2
    - [ ] GFM task list 3-3
- [ ] GFM task list 4
    - [ ] GFM task list 4-1
    - [ ] GFM task list 4-2

###Emoji mixed :smiley:

> Blockquotes :star:

####GFM task lists & Emoji & fontAwesome icon emoji & editormd logo emoji :editormd-logo-5x:

- [x] :smiley: @mentions, :smiley: #refs, [links](), **formatting**, and <del>tags</del> supported :editormd-logo:;
- [x] list syntax required (any unordered or ordered list supported) :editormd-logo-3x:;
- [x] [ ] :smiley: this is a complete item :smiley:;
- [ ] []this is an incomplete item [test link](#) :fa-star: @pandao; 
- [ ] [ ]this is an incomplete item :fa-star: :fa-gear:;
    - [ ] :smiley: this is an incomplete item [test link](#) :fa-star: :fa-gear:;
    - [ ] :smiley: this is  :fa-star: :fa-gear: an incomplete item [test link](#);
            
###TeX(LaTeX)
   
$$E=mc^2$$

Inline $$E=mc^2$$ Inline，Inline $$E=mc^2$$ Inline。

$$\(\sqrt{3x-1}+(1+x)^2\)$$
                    
$$\sin(\alpha)^{\theta}=\sum_{i=0}^{n}(x^i + \cos(f))$$
                
###FlowChart

```flow
st=>start: Login
op=>operation: Login operation
cond=>condition: Successful Yes or No?
e=>end: To admin

st->op->cond
cond(yes)->e
cond(no)->op
```

###Sequence Diagram
                    
```seq
Andrew->China: Says Hello 
Note right of China: China thinks\nabout it 
China-->Andrew: How are you? 
Andrew->>China: I am good thanks!
```

###End
