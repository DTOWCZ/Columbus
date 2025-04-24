[![enter image description here](https://www.wistron.cz/wp-content/uploads/2022/10/logo-light.svg)](http://www.wistron.cz)
# Markdown
Univerzální jazyk / nástroj v Prompt Engineeringu, který je potřebný k vytváření AI agentů, aby krásně formátoval odpovědi.
- 🤖 Jednoduché parsování: lehká syntaxe umožňuje AI rychle rozpoznat strukturu textu.  
- 🚀 Rychlá editace a náhled: podporuje živé úpravy a okamžitou zpětnou vazbu.  
- 🛠️ Univerzální rozšíření: ToC, úkolové seznamy, emoji a další rozšiřují možnosti interakce.  
- 🔒 Čisté HTML a bezpečnost: AI může bezpečně zpracovat vložené tagy a vyfiltrovat nechtěný obsah.  
- 📚 Přenosnost: kompatibilní s CommonMark, GitHub Flavored Markdown i dalšími nástroji napříč projekty.  
  - Open-Source: https://stackedit.io/app#
 ![](https://img.shields.io/github/stars/benweet/stackedit.svg) ![](https://img.shields.io/github/forks/benweet/stackedit.svg) ![](https://img.shields.io/github/tag/benweet/stackedit.svg) ![](https://img.shields.io/github/release/benweet/stackedit.svg) ![](https://img.shields.io/github/issues/benweet/stackedit.svg) ![](https://img.shields.io/bower/v/stackedit.svg)
  - Open-Source: http://editor.md.ipandao.com/en.html
![](https://img.shields.io/github/stars/pandao/editor.md.svg) ![](https://img.shields.io/github/forks/pandao/editor.md.svg) ![](https://img.shields.io/github/tag/pandao/editor.md.svg) ![](https://img.shields.io/github/release/pandao/editor.md.svg) ![](https://img.shields.io/github/issues/pandao/editor.md.svg) ![](https://img.shields.io/bower/v/editor.md.svg)
  - Visual Studio Code: https://code.visualstudio.com/

___
# Nadpis 1
## Nadpis 2
### Nadpis 3
#### Nadpis 4
##### Nadpis 5
###### Nadpis 6

Toto je H1
=

Toto je H2
-

## ***Efekty znaků a čáry atd.*** 
~~Přeškrtnutí~~ <s>Přeškrtnutí (při rozpoznávání HTML tagů)</s>
*Kurzíva*      _Kurzíva_
**Tučné**  __Tučné__
***Tučná kurzíva*** ___Tučná kurzíva___

Horní index: X<sub>2</sub>, dolní index: O<sup>2</sup>

**Zkratka (jako HTML tag abbr)**

> Tj. delší slova nebo fráze ve formě zkratek, ale musí být zapnuto rozpoznávání HTML tagů, je defaultně zapnuto

Specifikace <abbr title="Hyper Text Markup Language">HTML</abbr> je udržována <abbr title="World Wide Web Consortium">W3C</abbr>.

### Citace Blockquotes

> Citace text Blockquotes

Smíšené inline citace Blockquotes
                    
> Citace: Pokud chcete vložit prázdný řádek `tj. <br /> tag`, zadejte dvě nebo více mezer a poté stiskněte Enter[, obyčejný odkaz](http://localhost/).

### URL  odkazy
 - [Obyčejný odkaz](https://www.wistron.cz/) 
 - [Obyčejný odkaz s popisem](https://www.wistron.cz/ "Firemní webové stránky") 
 - Čistý odkaz: <https://github.com> 

[Kotva pro odkaz][anchor-id] 

[anchor-id]: https://www.wistron.cz/

### Zvýrazňování kódu v různých jazycích Codes
#### Inline kód
Spusťte příkaz: `npm install marked`

#### Styl s odsazováním
Tj. odsazení čtyřmi mezerami, také jako implementace funkce podobné `<pre>` předformátovaného textu (Preformatted Text).

    <?php
        echo "Hello world!";
    ?>
    
Předformátovaný text:

    | First Header  | Second Header |
    | ------------- | ------------- |
    | Content Cell  | Content Cell  |
    | Content Cell  | Content Cell  |

#### JS kód
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


#### HTML kód
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

##### HTML znaky
&copy; &  &uml; &trade; &iexcl; &pound;
&amp; &lt; &gt; &yen; &euro; &reg; &plusmn; &para; &sect; &brvbar; &macr; &laquo; &middot; 
X&sup2; Y&sup3; &frac34; &frac14;  &times;  &divide;   &raquo;
18&ordm;C  &quot;  &apos;

----

### Obrázky
Obyčejný obrázek:
![](https://www.wistron.cz/wp-content/uploads/2022/10/logo-light.svg)

Columbus (Obrázek + Popis + Odkaz)：
[![](https://columbus.wistron.com/img/b8da0987175a606f33430d002f93f571.png)](https://columbus.wistron.com/app/chatRoom "Popis obrázku")
                
----

### Seznam
#### Jednoduchý seznam - lze použít (-) nebo (*):

- Item A
- Item B
- Item C

* Item A
* Item B
* Item C

#### Seznam s vnořením:
                
+ Item A
+ Item B
    + Item B 1
    + Item B 2
    + Item B 3
+ Item C
    * Item C 1
    * Item C 2
    * Item C 3

#### Bodový seznam:
1. Item A
2. Item B
3. Item C
                
----
                    
### Tabulky
                    
First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell 
--
| Function name | Description                    |
| ------------- | ------------------------------ |
| `help()`      | Display the help window.       |
| `destroy()`   | **Destroy your computer!**     |
--

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
                
----

## Extra Markdown

###  Výjimky pro speciální znaky

\*literal asterisks\*

### GFM task list

- [x] GFM task list 1
- [x] GFM task list 2
- [ ] GFM task list 3
    - [ ] GFM task list 3-1
    - [ ] GFM task list 3-2
    - [ ] GFM task list 3-3
- [ ] GFM task list 4
    - [ ] GFM task list 4-1
    - [ ] GFM task list 4-2

### Kombinace s Emoji  :smiley:  :star:
- [x] :smiley: @označení, 🙋‍♂️ *#refs*, [odkazy](), **formátování**, a <del>tagy</del> jsou podporovány;
    - [ ]  :gear: Nedokončená položka;
- [ ] Pro dokončení klikni na tento link: [test link](#) 😂 - @Lisa; 
    - [X] Toto reprezentuje dokončený úkol :smiley:;
            
### Matematické výrazy ([KaTeX](https://khan.github.io/KaTeX/))
 - $$E=mc^2$$
 - $$\sin(\alpha)^{\theta}=\sum_{i=0}^{n}(x^i + \cos(f))$$
 - The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral


## Columbus zatím neumí                
### Kreslení vývojových diagramů Flowchart
```flow
st=>start: Login
op=>operation: Login operation
cond=>condition: Successful Yes or No?
e=>end: To admin

st->op->cond
cond(yes)->e
cond(no)->op
```

### Kreslení sekvenčních diagramů Sequence Diagram
                    
```seq
Andrew->China: Says Hello 
Note right of China: China thinks\nabout it 
China-->Andrew: How are you? 
Andrew->>China: I am good thanks!
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjE2MDY4OTUsLTE2MDMwNzA3OTFdfQ==
-->