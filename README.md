# IEEE-article-latex-template

## 说明

** 在Github上偶然发现的一个IEEE模板，使用方便，暂定为实验室通用的论文模板。使用该模板时，可通过Github的fork功能，或直接复制本repo。 **

<span>
<!-- LaTeX Logo -->
<img src="/figures/latex.png" width="200px" height="auto" hspace="20"/>
<!-- IEEE Logo -->
<img src="/figures/Ieee.jpg" width="200px" height="auto" hspace="20"/>
</span>

IEEEtran compliant LaTeX template. This document follows the official documentation provided at
the [IEEE](https://www.ieee.org/publications_standards/publications/authors/author_templates.html) and
the documentation developed by Michael Shell, the IEEEtran original author that provided a guide
``IEEEtran_HOWTO.pdf`` with all information needed to produce an IEEE compliant article in LateX.

The default configurations for this template are:

```latex
\documentclass[journal,twocolumn,letterpaper,10pt]{IEEEtran}
```
## Requirements:
* LateX: This will depend on your Operating System. You have to check how to install all Latex packages for your OS.
* Any text editor that supports LateX (e.g. [Atom](https://atom.io/), [Sublime Text](http://www.sublimetext.com/), [Emacs](https://www.gnu.org/software/emacs/), etc.)
* LaTeX plugins for your text editor (this is optional, but it will make your life easier).
I you use Atom (that is my case) the following ones are available:
  * [language-latex](https://atom.io/packages/language-latex)
  * [latex](https://atom.io/packages/latex)
  * [latexer](https://atom.io/packages/latexer)

## Usage
To use this template, you can simply fork or copy this repository and start working on it.



### Starting your Article -- 开始撰写论文
The first thing that you need to do is to update the article's title and author information at the ```variables.tex```
file.


修改文件"variable.tex"中的内容，如下：

```latex
% Article Title
\def \ArticleTitle{Your Article Title}
% Author name
\def \AuthorA{Your Name}

%一般，以下内容不需要修改：
% Author(s) Email(s)
\def \AuthorAemail{cuiziqiang@tju.edu.cn}

% Institution(s) Name(s)
\def \InstitutionA{\textit{Tianjin Key Laboratory of Process Measurement and Control} \\
\textit{School of Electrical and Information Engineering}\\
Tianjin University, Tianjin 300072, China}
```
If you article has multiple authors and/or institutions, you must edit this information at ```variables.tex```
file by defining new variables and updating the respective commands. The information regarding how to
have multiple authors/institutions is available at ``IEEEtran_HOWTO.pdf``.



%以下，可通过编辑相关文件修改摘要、关键词和正文。

### Abstract
### Keywords


### Sections
Sections are located at ```sections```folder.
Initially, there are multiple files in this folder, i.e.

```sections/sec_intro.tex```
```sections/sec_method.tex```
```sections/sec_results.tex```
```sections/sec_cons.tex```

In the file ```article.tex```, the aforementioned tex files are organized as below 

```latex
\input{section/sec_intro.tex}
\input{section/sec_method.tex}
```
Now get to work and start writing your article.


### Figures
Image files go to ```figures``` directory.
Place your files here and include them in the body of your document.

### Bibliography
The bibliography is in a ``.bib`` file located at ```bib.bib```.

The IEEEtran specification requires that to print the article bibliography you must have at least
one citation in you document, otherwise you will get a compilation error. To fix that issue we
define the ``hasBibliography`` variable that us located at the variables file:

```latex
\def \hasBibliography{1}
```
The default value specifies that the bibliography must be generated. If you don't want, just that change the variable value to 0.

To cite a bibliography entry in your document you can use the following command:

```latex
\cite{johndoe}
```

### Acronyms
The list of acronyms is located at ```acronyms/acronyms.tex```.  To define a new acronym in your document you must define the new entry in that file:

```latex
\newacronym{<label>}{<abbreviation>}{<full>}
```
To reference an acronym you can use:

```latex
\gls{<label>}
```
If you are referring the acronym for the first time it will show in you document the ```<abbreviation>``` and
```<full>``` tags. At the remaining references it will show only the ```<abbreviation>``` tag.

To reference an acronym in the plural form you can use the following command:

```latex
\glspl{<label>}
```

The full documentation of the ```acronyms``` package is available at [LaTeX Glossary Wiki](https://en.wikibooks.org/wiki/LaTeX/Glossary)



## 编译


You have some ways to create the final pdf:

### Using the text editor
It depends on the text editor you are using.
If you are using Atom and the LaTeX plugin, just press
<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>B</kbd>

### 使用脚本
脚本是一种高效的工作方式，化繁为简。在Windsows下，需要安装git软件（https://gitforwindows.org/），直接双击即可运行。
建议：每次在提交（commit）前，运行一次toPDF.sh 和 clean.sh。

If you have the complete LateX environment installed, you can run the ```toPDF.sh``` script to generate the PDF (```article.pdf```):
```
$ sh toPDF.sh
```

To clean the files generated at the compilation process, you can run ```clean.sh``` script:
```
$ sh clean.sh
```

