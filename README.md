
# Identifying and Correcting Data Anomalies in E-commerce Customer Data

# Problem: 
E-commerce businesses often struggle with inaccurate or incomplete customer data, which can lead to inefficiencies in marketing campaigns, customer service interactions, and fraud detection efforts.

# Solution: 
Implementing EDA techniques allows e-commerce businesses to identify and correct data anomalies in customer records, such as missing values, invalid formats, and outliers.

# Results:

- A 20% reduction in customer data errors, leading to increased accuracy in marketing campaigns, customer segmentation, and fraud detection.

- A 15% improvement in customer service efficiency, as accurate customer data enables faster resolution of inquiries and issue

##  An Exploratory data analysis APP


![APP](https://drive.google.com/uc?id=1fPtlPEvcwhZAye_iHkac5QHAnQjnSlMh&export=download)


## TAPIWA CHAMBOKO
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://tapiwachamb.github.io/tapiwachamboko/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tapiwa-chamboko-327270208/)
[![github](https://img.shields.io/badge/github-1DA1F2?style=for-the-badge&logo=githubr&logoColor=white)](https://github.com/tapiwachamb)


## 🚀 About Me
I'm a full stack developer experienced in deploying artificial intelligence powered apps


## Authors

- [@Tapiwa chamboko](https://github.com/tapiwachamb)


## Acknowledgements

 - [dataprofessor](https://github.com/dataprofessor)
 - Pandas Profiling in Data Science
 


## Demo

**Live demo**

[Click here for Live demo](https://data-eda.streamlit.app/)
## Installation

Install required packages 

```bash
  pip install streamlit
  pip install pycaret
  pip insatll scikit-learn==0.23.2
  pip install numpy
  pip install seaborn 
  pip install pandas
  pip install matplotlib
  pip install plotly-express
  pip install streamlit-lottie
```
    
## Datasets
- Drop your Datasets in the app to get resuilts
- you can use he exaple data provided in the app
## Code

```bash
import streamlit as st
import pandas as pd  
import plotly.express as px  
import base64  
from io import StringIO, BytesIO  
import numpy as np
import pandas as pd
from sklearn import datasets
import matplotlib.pyplot as plt
from pandas_profiling import ProfileReport
from streamlit_pandas_profiling import st_profile_report

def app():
    st.markdown('''
# **Exploratory data analysis App**
Please upload your xlsx file or click the button below to use example dataset
---
''')

# Upload CSV data
    with st.sidebar.header('Upload your XLSX data'):
        uploaded_file = st.sidebar.file_uploader("Upload your input XLSX file", type=["xlsx"])
       

    # Pandas Profiling Report
    if uploaded_file is not None:
        @st.cache
        def load_csv():
            csv = pd.read_excel(uploaded_file,engine='openpyxl')
            #csv = pd.read_csv(uploaded_file,encoding='latin1', index_col=None,usecols = "A,B,C,D,E,F,H,G,H,I,J")
            return csv
        df = load_csv()
        pr = ProfileReport(df, explorative=True)
        st.header('**Input DataFrame**')
        st.write(df)
        st.write('---')
        st.header('**Exploratory data analysis Report**')
        st_profile_report(pr)
        
    else:
        st.info('Awaiting for XLSX file to be uploaded.')
        
        if st.button('Press to use Example Dataset'):
            # Example data
            @st.cache
            def load_data():
                a = pd.DataFrame(
                    np.random.rand(100, 5),
                    columns=['a', 'b', 'c', 'd', 'e']
                )
                return a
            df = load_data()
            pr = ProfileReport(df, explorative=True)
            st.header('**Input DataFrame**')
            st.write(df)
            st.write('---')
            st.header('**Exploratory data analysis Report**')
            st_profile_report(pr)

```


## Deployment

To deploy this project we used streamlit to create Web App
- Run this code below

```bash
  streamlit run app.py 
```


## Appendix

Happy Coding!!!!!!


