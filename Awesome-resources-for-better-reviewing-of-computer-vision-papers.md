## Awesome  resources for better reviewing of computer vision papers

### Official advice 

- [ICCV 2021 reviewer instructions](http://iccv2021.thecvf.com/node/39): (or equivalent for the conference you are reviewing for) this will give you the minimum guidelines to follow
- [CVPR 2020 reviewer tutorial power point](http://cvpr2020.thecvf.com/sites/default/files/2019-09/CVPRReviewerTutorial.pptx) Short slide deck with good/average/bad reviewing examples

### Additional recommandations

- [CVPR 2020 workshop on reviewing video](https://www.youtube.com/watch?v=RIIQ7ohRyZw) if you have a lot of time (5hours in total !)  

<details> <summary> Take-home messages </summary> 

Jordi Pont-Tuset:
  
- check papers right when assigned to prevent discovering problems which request area-chair intervention at the last minute 
- read paper & mark comments
- group comments by topic
- **didactically** write down comments about each group, assuming minimal background knowledge

Fatma Güney:
- Critical thinking: question, doubt, clarify your questions
- Constructive input: Explain what is missing, provide suggestions for inprovement, specific & detailed
- Empathy: Respect the work, proper, ideally encouraging language
  
Conrad Schindler:
- Novelty: remember that new ideas are **rare**, better questions are "would this be of interest to the people attending the conference/reading the journal", "Does the work contribute to advancing the domain"
  
</details>

### Personal recommendation


<details> <summary> How I write my reviews. </summary> 

- **Read the reviewing material.** Each conference usually provides reviewing guidance. I look them up and go through any available resources (text and tutorials) before reading any of the assigned papers. This insures I am aware of **conference-specific instructions** (is dataset release recommended or mandatory ? Should authors provide code for their submission ?) and is usually also a good refresher on reviewing best practices.
- **Focus on the readers**. I keep in mind that my review will be read by the authors, the area chair as well as the other reviewers.
  - **Provide actionable feedback**. For the authors, I try to set my mindset to **"How do I help them improve their paper?"**
    - If I am leaning towards rejection I try to think "What changes could they make that would lead me to accept their paper ?"
    - If I am leaning towards acceptance "How could they make it an even stronger submission ?"
  - For the area chair and other reviewers, I try to summarize as synthetically and didactically as I can my analysis and reasons for acceptance/rejection.

- **Save the readers' time**. I try to reduce the load on the reader by:
  - **Reducing the readers' search load**. I try to **provide** as many **links and references** as I can so that people can easily navigate to specific locations in the paper or other resources.
     - If I am referring to a specific sentence in the paper I will copy-paste it if it is short and can be understood in isolation, otherwise I will provide the lines I am referring to (for instance `l216` or `l216-218`).
     - Similarly, I will point to tables and figures by their name, providing additional details to guide the reader to the specific location of interest (e.g. "in the top row of Table 5, where the paper investigates the effect of adding their novel block to standard architectures, (...)")
     - If I point to a reference I provide the first authors' last name, the conference, the name of the paper and when possible a link to the paper so that readers can directly access it having to search for it.
  - **Sorting and naming the main points** of my review. For instance, I will sort the strengths and weaknesses from most critical to least important, indicating the order. For instance I will write something along the lines of
    ```
    Below, I list the strengths and weaknesses from most to least critical.
    S1. Qualitative results.
    More details about why I found the qualitative results really awesome.

    ...
    S4. Ablation study.
    More details on why I found that the ablation studies supported the claims of the paper.
  
    ```
    I find this facilitates later discussions, as we can discuss the different points by easily referring to them.

- **Use the summary as an opportunity to help the readers understand what factored most into my decision**. In the justification of my review summary, I try to make it very explicit how the strengths and weaknesses have affected my final reading. For instance, I will group the weaknesses between the ones that motivate my rejection and the ones that have a more marginal impact on my rating.

- **Typos and writing errors**:
  - I try to **assess** whether the errors and typos **affect my understanding** of the paper, **affect my reading fluidity**, or are **minor** and don't really impact my understanding or ease of reading. I explicitly mention the level at which the errors affect my understanding. I also try to remember that in many cases, english might not be the primary language of the authors (although I do generally expect authors to proofread and use automatic spell checking whether english is or is not their first language). 
  - If there is a small number of typos (less than 1 per paragraph). I provide an exhaustive list.
  - If they are numerous.
    - I provide an illustration of the density by listing all typos in a subset of the text. This will usually look like:
      ```
      l215: Our method doe -> Our method does
      l216: previous work In our method -> previous work. In our method
      ...
      ```
  - If the errors affect my understanding of the paper, I include it in the weaknesses.
</details>

