# Advice for better writing

This page is an effort to gather the advice I can find on how to write a good paper, with as focus on top-tier computer vision conferences (CVPR, ECCV, ICCV) 

</details>

## Follow guidelines

Read author *and* reviewer guidelines to know how not to get rejectet *and* how to get accepted

<details> <summary> <a href="http://cvpr2018.thecvf.com/submission/main_conference/reviewer_guidelines">CVPR 2018 reviewer's guidelines </a> </summary>

#### What to Look For

> **Minor flaws** can be corrected and **shouldn't be a reason to reject a paper**

> **Embrace novel, brave concepts**

> The fact that a proposed method does **not exceed the state of the art accuracy on an existing benchmark dataset is not grounds for rejection by itself**.

> Acceptance and rejection decisions should not be determined solely by the method's raw performance

> It is important to **weigh both the novelty and potential impact of the work alongside the reported performance**

> Each paper that is accepted should be **technically sound** and **make a contribution to the field**.

</details>

## Writing advice from those who know best !

<details> <summary> <a href="https://www.cc.gatech.edu/~parikh/citizenofcvpr/static/slides/malik_write_good_paper.pdf"> <b> Jitendra Malik's </b> write a good paper slides 2018</b></a> </summary>

> Possible introduction style: What did you do (Fig. 1), How did you do it? (Fig. 2)

> The best way to write a paper is to first give a talk on it

> Introduction section: The most important section of a paper. For me, once I have finished reading the introduction, I have formed an opinion of whether to accept or reject the paper
</details>


<details> <summary> <a href="https://www.cc.gatech.edu/~parikh/citizenofcvpr/static/slides/freeman_how_to_write_papers.pdf"><b>Bill Freeman's</b> 2018 slides on writing a good CVPR submission </summary>

> I can’t stand “future work” sections. It’s hard to think of a weaker way to end a paper

> Omit needless words

> Figure captions should be self-contained and the caption should tell the reader what to notice about the figure

> There are perceived pressures to over-sell, hide drawbacks, and disparage others’ work.  Don’t succumb.

(and previous [2014 version](https://billf.mit.edu/sites/default/files/documents/cvprPapers.pdf))
</details>

## Practical tips

#### LaTeX

<details> <summary> Structure </summary>
Typically 
- a *main* file named `00submission_id.tex`
- references in the main file to each section is a **separate file**
 
*00submission_id.tex*
```latex 00submission_id.tex
\documentclass[10pt,twocolumn,letterpaper]{article}

\usepackage{times}
\usepackage{epsfig}
\usepackage{graphicx}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage[dvipsnames]{xcolor}
\usepackage[numbers,sort,compress]{natbib}
\begin{document}

\title{My Awesome Paper}

\author{
 Me \textsuperscript{1} \thanks{This work was performed during an internship at Microsoft.}
 \qquad Author 2 \textsuperscript{2}
 \qquad Author 3 \textsuperscript{2}\\
 \\ \\
 {\normalsize \textsuperscript{1}My affiliation \textsuperscript{2} Other affiliations} \\
}

\maketitle

\input{abstract}
%%%%%%%%% BODY TEXT
\input{introduction}
\input{relatedwork}
\input{method}
\input{experiments}
\input{conclusion}
%%%%%%%%% BODY TEXT
\clearpage \newpage
{\small
\bibliographystyle{ieee_fullname}
\bibliography{egbib}
}
```

*abstract.tex*
```
\begin{abstract}
We did something awesome and wrote about it.
\end{abstract}
```

*introduction.tex*
```
\section{Introduction}
% Why the task you address is important, (if it is a new problem) problem statement, and applications

% Challenges and the overview of pioneering works 

% Remaining limitations

% Our method in a glance 

% Clearly stated contributions
Our contributions can be summarized as follows:
\begin{itemize}
	\item{We propose a new method for ...}
	\item{We demonstrate...}
	% \item{We further present...}
\end{itemize}

% The summary of the results
```

*relatedwork.tex*

```
\section{Related Work}
\label{sec:related}

% Define the scope of the related work, grouping the works by theme (tackling the same problem, or using similar methods, ...)

We first review the literature on {relevant field}.
Then, we focus on methods which {relevant approaches}, and {other related topic}.


\paragraph{relevant field.}
Most approaches in the literature tackle the problem of estimating either hand or object pose, separately.

% ...
```

...

</details>

<details> <summary> One color per author </summary>

Assign colors to authors in main latex file: 

```latex
\newcommand{\Yana}[1]{\textcolor{red}{#1}}
\newcommand{\Author2}[1]{\textcolor{green}{#1}}
% Add author with custom color custom colors
\definecolor{mycolor}{RGB}{219, 122, 48}
\newcommand{\Author3}[1]{\textcolor{mycolor}{#1}}
```

Add comments in text 

```latex
\Yana{I think we should ...}
\Author2{Should we keep ... ?}
```

</details>
  
<details> <summary> Bibliography (bibtex) </summary>
- use [natbib](http://merkel.texture.rocks/Latex/natbib.php) 

`\usepackage[numbers,sort,compress]{natbib}` so that references are sorted in ascending number ([13, 3, 34] --> [3, 13, 34])

- Make references **homogeneous**
    - Good sources of bibtex files are usually the **publication websites** 
         - for CVPR/ICCV/ECCV I use the openaccess search websites. For instance for CVPR'19: [http://openaccess.thecvf.com/CVPR2019.py](http://openaccess.thecvf.com/CVPR2018.py) where I can search for the paper (by author/paper title) and copy the bibtex (same applies for [CVPR'18](http://openaccess.thecvf.com/CVPR2018.py), [CVPR'17](http://openaccess.thecvf.com/CVPR2017.py), ..., [ICCV'19](http://openaccess.thecvf.com/ICCV2019.py), [ECCV'18](http://openaccess.thecvf.com/ECCV'18.py), ...
         
         - for NeurIPS each paper has [a page](https://papers.nips.cc/paper/7181-attention-is-all-you-need) from which the bibtex can be copied
    - To minimize efforts to make homogeneous, remove all unecessary fields (month, page numbers, abstract, url, ...) from the bibtex
    - Check that all names are in full letters (no initials except for middle names)
    - Everytime a conference is referenced, it should have **exactly** the same name, typically the one the conference uses in their own offical bibtex (`{Advances in Neural Information Processing Systems}` for NeurIPS, `{The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)}` for CVPR, `{The European Conference on Computer Vision (ECCV)}` for ECCV), {The IEEE International Conference on Computer Vision (ICCV)} for ICCV, ... (Can't get it wrong by taking the official version !)
    - in a final pass, look at how the references are rendered in the PdF, and check for consistency
  
</details>

<details> <summary> Appendix sections with Letter numbering </summary>
```latex
\usepackage{titletoc}
\renewcommand{\thesection}{\Alph{section}}
% ...
\begin{document}
```
</details>
