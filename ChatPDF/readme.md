
<a name="readme-top"></a>


<h1 align="center"> Self ChatPDF </h1>



<div align="center">
    <img src="./img/UniApplyLogo.png" width=160, height=150>
    <p>
    This is a PDF summarization Chatbot through RAG implementation by langchain and streamlit.
    <br>  
    Ask freely and get the most accurate information with your odf files.
    <br>
    <h4 align="center">
    <p>
        <a href=#about-the-project>About</a> |
        <a href=#new-updates>News</a> |
        <a href="#project-lists">Projects</a> |
        <a href=#getting-started>Getting Started</a> |
        <a href=#usage>Usage</a> |
        <a href="#roadmap">Roadmap</a> |
        <a href="#contributing">Contributing</a> |
        <a href="#license">License</a> 
    </p>
  </h4>
  </p>
</div>

# About the project
This is an implementation of the Retrieval-Augmented Generation (RAG) model by [Langchain](https://www.langchain.com/), and a chatbot interface built with [Django](https://www.djangoproject.com/) using application F&Q collected from universities around the world. 

<div align="center">
<p class="image-cropper">
    <img  src = "./img/UniApply_demo.gif" />
</p> UniApply Interface 
</div>
<br>

Regarding the RAG, we prepare the data in advance instead of implementing real-time retrieval. Since most application information do not vary much throughout the year, we only have to update the information yearly, therefore there is no need to do realtime search to lower the computation and development cost.   
The vector-databse we use in this project is created using [FAISS](https://faiss.ai/index.html), it is a library for efficient similarity search and clustering of dense vectors. The embedding and generation model we use is offered by OpenAI GPT-3.5 for comparison.
<p align="center">
<img src="./img/model_structure_explain.gif" alt="drawing" width="400" height="200"/>
<br> The Implementation of Partial RAG </br>
</p>

The results showed that with the RAG implemented with our model, it can providing accurate information and link for your reference. This mechanism also allows user to ask free form questions, instead of looking through the F&Q going through the questions one by one or `ctrl-F` and try to figure out which is the correct answer, non-native speakers and also confused user can easily get the right answer. 
<p align="center">
<img src="./img/gpt_result.png" alt="drawing" width="420" height="240"/><img src="./img/gpt_rag_result.png" alt="drawing" width="400" height="240"/>
<br> Comparison on GPT-3.5 and GPT3.5 with RAG </br>
</p>

# New Updates
>　🎉　UniApply is born on Jan 16, 2024

* 2024-01-19: Multi-lingual is available, news update section is on the web 
* 2024-01-18: Schools are added in the list now ~~~~~~~~~~~~~~~~
* 2024-01-17: The first version of UniApply is available


<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Getting Started
## Installation
```bash
Python=3.8 above
!pip install langchain langchain-community pypdf sentence_transformers chromadb tiktoken openai
```
## ENV VAR setting
```bash
export "OPENAI_API_KEY" = 'YOUR_OPENAI_KEY'
export "DJANGO_SECRET_KEY" = 'YOUR_DJANGO_SECRET_KEY'
```
## Run
```
cd UniApply_Chatbot
python manage.py runserver 8003 -- you can change port 
```
## Add your own data
You can put your own data in the data folder under `./UniApply_Chatbot/data/`, the file should be in excel (`.xlsx` ) format.

Also the columns are Question, Answer, Tags, Link respectively.
* **Question**: The questions from the F&Q
* **Answer**: The corresponding answer from the F&Q
* **Tags**: Stores the school, department, degree and category information, for example: USC , Vertibi, Master, PhD, Application
* **Link** : link of the F&Q website

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Usage
The overall structure of this project, you can modify it as you like, also any recommendation is welcomed.
### Important files
* `./UniApply_Chatbot/data/` : the folder where we store the f&q data to be put in the vector space
* `manage.py`: the file that runs everything `main` is in here
* `view.py`: modify responce and custom prompt templates
* `static`, `template`: modify the appearance of the chatbot under here
```bash
└──LLM_RAG_UniApply
   ├──UniApply_Chatbot # the whole django project
   │  ├──data 
   │  ├──UniApply_Chatbot
   │  ├──manage.py 
   │  ├──db.sqlite3
   │  └──UniApply # the chatbot
   │     ├──static 
   │     ├──admin.py
   │     ├──templates 
   │     ...
   │     └──views.py 
   ├──LICENSE
   ├──README.md
   └──img
```
<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Roadmap
- :heavy_check_mark: Bilingual or multi-lingual support
- [ ] Better Interface
    - [ ] press enter to send message
    - [ ] expandible text entering box
- [ ] Able to change embedding and generating models, including Llama, TWLlama or ChatGLM...
- :heavy_check_mark: More schools and departments to be added 
- [ ] Personalized upcomming deadline alerts and organized planning table to be created 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star 🌟🌟🌟 Thxxx 🌟🌟🌟

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->
# License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Other Projects
* [LLM Projects](https://github.com/stephanie0324/Finetune_LLM)
* [Web-Scraping](https://github.com/stephanie0324/Web-Scraping-)
* [Machine Learning with me](https://github.com/stephanie0324/ML_practrice)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://github.com/stephanie0324/" target="blank"><img align='center' src= "https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="steph0324"  /></a> <a href="https://www.facebook.com/profile.php?id=100005029028402&locale=zh_TW" target="blank"><img align="center" src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="steph0324" /></a>
<a href="https://www.linkedin.com/in/stephanie-chiang-42100b165/" target="blank"><img align="center" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="steph0324"/></a>
<a href="https://www.instagram.com/yrs_2499?igsh=MXJ5MHNpc2ZxNHh5NA%3D%3D&utm_source=qr" target="blank"><img align="center" src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="steph0324" /></a>
<a href="https://www.youtube.com/channel/UCpIrOv7O2R7HfpCEMQEOOKQ" target="blank"><img align="center" src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="steph0324" /></a>
</p>
