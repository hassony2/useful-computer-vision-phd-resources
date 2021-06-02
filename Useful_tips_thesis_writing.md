## Useful tips for thesis writing (Work in progress, just like the thesis itself ;) )

(Many/most of these I learnt from [Gül Varol](https://github.com/gulvarol) !)

### Additional recommandations

#### Setting up

- Find a template (`mithesis` for instance)
- Ask your supervisor for examples of well-written thesis

#### Preparing latex 
- Useful commands to create placeholders 
  - Placeholder figure : Add `\newcommand{\draftfig}[1]{\fbox{\parbox[c][1in][c]{\textwidth}{#1}}}` before `\begin{document}` and then create figures with `\draftfig{Description of what the figure will be}` 
  - Highlighted TODO text: Add `\newcommand{\TODO}[1]{\textcolor{red}{TODO: #1}}` before `\begin{document}` and then use `\TODO{Here say what you plan to do in the future.}`

#### Generic advice

- Add many illustrations (We are in computer vision :) but also probably true for any thesis ! )
- Make many connexions between sections (point to figures, to other relevant sections, ...)
- All figures/tables should be referenced in the text
- Make extra-sure you are citing relevant literature from your jury
- `Ctrl + F` "this paper" and replace with "this work"
