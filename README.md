# latex-template

Created by : Erestu Zhang.

2019 / 12 / 17 @Nanjing

---

## How to use _Latex_ on Ubuntu

check [Ubuntu下Latex安装及中文配置](https://www.jianshu.com/p/d185aad1f915)

1. Install Tex Live: Basic LaTex packages.
   * `sudo apt-get install texlive-latex-base`
2. Installs all LaTex CJK packages.
   * `sudo apt-get install latex-cjk-all`
3. Install some LaTeX supplementary packages
   If you need some other packages,run
   * `apt-cache search lastpage`,
    then you will see:
   * `exlive-latex-extra - TeX Live: LaTeX supplementary packages`
   * finally,just install it by running `sudo apt-get install texlive-latex-extra`
4. Install a texmaker,it's a graphical user interface for editing.
   * `sudo apt-get install texmaker`
5. For using `xelatex` for chinese using.
   * `sudo apt-get install texlive-xetex`
6. support for cmd `apt-cache show texlive-publishers`
   * `sudo apt-get install texlive-publishers`
7. open `Texmaker`
   * search->type`Texmaker`
   * double click
   * you'll see the icons of `new` and `open` ,etc.
   * there are two right arrows on the top,and two select boxs,for the first select box,you can choose to build `Latex` or `Bibtex` ,etc. For the second select box,you can choose to check `PDF` or `PS`,etc.After chosing the function you want,click the first arrow,then click the second arrow.
   * ![texmaker][5]
   * ![texmaker][1]
   * ![texmaker][2]
   * ![texmaker][3]
---
### How to use _Latex_ on VSCode
* After installing [VSCode](https://code.visualstudio.com/), 
* install extension `LaTex Workshop`
* edit file->preferences->Settings->settings.json
  ```
  "latex-workshop.latex.tools": [
          {
              "name": "latexmk",
              "command": "latexmk",
              "args": [
                  "-synctex=1",
                  "-interaction=nonstopmode",
                  "-file-line-error",
                  "-pdf",
                  "%DOC%"
              ]
          },
          {
              "name": "xelatex",
              "command": "xelatex",
              "args": [
                  "-synctex=1",
                  "-interaction=nonstopmode",
                  "-file-line-error",
                  "%DOC%"
              ]
          },
          {
              "name": "pdflatex",
              "command": "pdflatex",
              "args": [
                  "-synctex=1",
                  "-interaction=nonstopmode",
                  "-file-line-error",
                  "%DOC%"
              ]
          },
          {
              "name": "bibtex",
              "command": "bibtex",
              "args": [
                  "%DOCFILE%"
              ]
          }* install extension `LaTex Workshop`
      ],
      "latex-workshop.latex.recipes": [
          {
              "name": "xelatex",
              "tools": [
                  "xelatex"
              ]
          },
          {
              "name": "pdflatex",
              "tools": [
                  "pdflatex"
              ]
          },
          {
              "name": "latexmk",
              "tools": [
                  "latexmk"
              ]
          },
          {
              "name": "pdflatex -> bibtex -> pdflatex*2",
              "tools": [
                  "pdflatex",
                  "bibtex",
                  "pdflatex",
                  "pdflatex"
              ]
          }
      ],

  ```
* restart `VSCode`
* choose `your_tex_file.tex`
* `ctrl + allt + B` or click the icon on the left bar,click `tex` first and then `recipe:xelatex->bibtex->xelatex*2` and `View in VSCode tab`

  ![tex][4] 
### How to use _Bibtex_ on Latex

1. create `Bibtex` file and save as `ref.bib`.
2. for example ,edit
   ```
    @article{goodfellow2014generative,
      title={Generative Adversarial Nets},
      author={Goodfellow, Ian and Pougetabadie, Jean and Mirza, Mehdi and Xu, Bing and Wardefarley, David and Ozair, Sherjil and Courville, Aaron and Bengio, Yoshua},
      pages={2672--2680},
      year={2014}}
   ```
   and save the file.
3. add cite package in tex file
   add `\usepackage{cite}` behind `\documentclass`
4. add citation setting,put
    ```
      \bibliographystyle{plain}
      \bibliography{ref}
    ```
    infront of `\end{document}`
        * `\bibliography{ref}` indicates the bib file created above.
        * `\bibliographystyle{plain}`specifies the presentation of references. There are 8 options for common preset styles, which are:

           1. plain, arranged in alphabetical order, the comparison order is author, year and title;
           2. unsrt, the style is the same as plain, but in order of reference;
           3. alpha, using the first letter of the author's name + the last two years as the label, sorted alphabetically;
           4. abbrv, similar to plain, changes the month to the abbreviation, which is more compact;
           5. ieeetr, journal style of the International Institute of Electrical and Electronics Engineers;
           6. acm, journal style of American Computer Society;
           7. Siam, Journal of the American Academy of Industrial and Applied Mathematics;
           8. apalike, journal style of the American Psychological Association;
5. add citation
   * `\cite{goodfellow2014generative}`
   * `ctrl + allt + B` or click the icon on the left bar,click `tex` first and then `recipe:xelatex->bibtex->xelatex*2` and `View in VSCode tab`
     ![tex][4] 
6. export as PDF
   * or use the `TexMaker`,generate `Bibtex` first and then the PDF file.
   * ![texmaker][1]
   * ![texmaker][2]
   * ![texmaker][3]
  
---

## Examples

* [normal latex template](latex_template/nomal_latex)



It is the project of recording daily used templates.


---

## Reference

https://github.com/mrdrivingduck/svd-image-compression

https://www.jianshu.com/p/d185aad1f915

https://blog.csdn.net/m0_37041325/article/details/81171736

https://blog.csdn.net/npe_ml/article/details/82912570

---



  [1]: https://blog.erestu.top/usr/uploads/2019/12/1145651088.png
  [2]: https://blog.erestu.top/usr/uploads/2019/12/3751842155.png
  [3]: https://blog.erestu.top/usr/uploads/2019/12/1070040880.png
  [4]: https://blog.erestu.top/usr/uploads/2019/12/3708872102.png
  [5]: https://blog.erestu.top/usr/uploads/2019/12/2766675438.png