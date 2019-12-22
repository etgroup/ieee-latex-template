# IEEE-article-latex-template

## 说明

在Github上偶然发现的一个IEEE模板，使用方便，暂定为实验室通用的论文模板。使用该模板时，可通过Github网页上的“Use this template”。

## 文件夹的使用

为避免REPO文件过大，对文件夹的使用做以下约定：

1. 论文直接用到的图像文件，如pdf、jpg、png、eps等，才可以放置于figure/下，且要求：单个文件不超过5MB；
2. 论文用图的源文件及各种数据文件，如visio、mp、excel、mat等，都放置在根目录的exclude文件夹下。
3. 在.gitignore文件中添加exclude，这样所有exclude文件夹下的文件都不会同步到github上，可从而避免repo过大。


## Starting your Article -- 开始撰写论文
The first thing that you need to do is to update the article's title and author information at the ```article.tex```
file.


修改文件"article.tex"中的内容，如下：

```latex
\newcommand {\GSAuthor} {Graduate~Students}

% Author(s) Name(s)
\def \AuthorA{
    Ziqiang~Cui,~\IEEEmembership{Member,~IEEE,}
    \GSAuthor,
    Huaxiang~Wang,~\IEEEmembership{Senior~Member,~IEEE}% <-this % stops a space
\thanks{This research is financially supported by NSFC, Nos. 61671319 and 61627803.}% <-this % stops a space
\thanks{Manuscript received August 19, 2019; revised August 26, 2019.}}

% Article title
\title{My First IEEE Paper}

```




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

对于使用CTex软件来说，使用Winedt中的pdflatex编译即可。

## 使用脚本

脚本是一种高效的工作方式，化繁为简。在Windsows下，需要安装git软件（https://gitforwindows.org/）, 直接双击即可运行。
建议：每次在提交（commit）前，运行一次toPDF.sh 和 clean.sh。

If you have the complete LateX environment installed, you can run the ```toPDF.sh``` script to generate the PDF (```article.pdf```):
```
$ sh toPDF.sh
```

To clean the files generated at the compilation process, you can run ```clean.sh``` script:
```
$ sh clean.sh
```
## 检查论文格式

具体参考：
https://github.com/etgroup/paper_checklist

