# Evaluating Collaborative Filtering based Algorithms for Mobile Applications Based on Implicit Feedback

Analysing users' behaviour and creating explicit ratings from it to define the users' interaction with the predesigned layouts of an android mobile application.
This data is then used to train and test two Collaborative Filtering (CF) based Recommendation Systems (RS). Both models such as Item_Based CF (IBCF) and Matrix Factorization (MF) are evaluated in an offline environment using Statistical and Descision support accuracy metrics.

## Data Collection

- For the experiment, an android application is developed to collect the users' behaviour or implicit feedback
- User behavioural data is collected using Firebase and Google analytics APIs before saving into the serverless BigQuery Data Warehouse
- SQL is used to extract the data from BigQuery
- Extracted data is exported to google drive.
- Implemented an adaptive User Interface with the help of CF based recommendation system.

### Datasets:

- Users' implicit feedback
- normalized users-layouts ratings
  - generated from users' implicit feedback

---

**_NOTE:_**

- Users' implicit feedback dataset

  - only used in "data_preprocessing.ipynb"
    - all the datasets are already available and imported from google drive, so no need to import the data
    - Users' implicit data dataset can also be accessed from the local directory
      - "datasets/user_implicit_data" contains users implicit feedback dataset

- Models' evaluation dataset
  - used to train and test the models
  - can be accessed from:
    - local directory "datasets/users-layouts ratings" contains scaled data
    - or from the drive already implemented in teh required files
  - drived from the users' implicit feedback

---

### Recommendation Techniques:

- Collaborative Filtering Recommendation System
  - Item_Based Collaborative Filtering
  - Matrix Factorization

## Thesis Code Structure:

Thesis folder contains three directories and one pdf file:

- directories
  - user behaviour data
  - Recommend Layouts
  - Android Application
- file
  - Thesis_Report.pdf

### User behaviour data contains 2 directories and 3 files;

- directories
  - datasets
  - models
- files
  - data_preprocessing.ipynb
  - item_based_CB.ipynb
  - matrixFactorizationModel.ipynb

### Recommend Layouts contains 5 directories and 3 files

- directories
  - datasets
  - include
  - lib
  - models
  - scripts
- files
  - app.py
  - recommender.py
  - requirements.txt

### Android Application contains 2 directories

- APK
  - app-debug.apk
- AUI_AndroidProject

# Thesis Code Enviornment:

## user behaviour data

Models' evaluation and data pre-processing

### virtual environment settings

install virtualenv using

```
$ pip install virtualenv
```

Enable virtual enviornemnt:

```
$ .\.myThesis\Scripts\activate
```

### Required Libraries and packages to reproduce our results

- All libraries will be installed using pip command on notebook cell.

  - !pip install numpy

- Following are the neccessary libraries with versions:

  - pip 21.2.4
  - scipy 1.7.1
  - numpy 1.19.5
  - matplotlib 3.4.3
  - requests 2.25.1
  - seaborn 0.11.2
  - pandas 1.3.2
  - scikit-learn 0.23.2
  - math 1.2.1

  - attrs==21.2.0
  - autopep8==1.5.7
  - backcall==0.2.0
  - certifi==2020.12.5
  - cffi==1.14.6
  - chardet==4.0.0
  - click==8.0.0
  - colorama==0.4.4
  - crypto==1.4.1
  - cryptography==3.4.7
  - cycler==0.10.0
  - debugpy==1.5.0
  - decorator==5.1.0
  - Deprecated==1.2.12
  - entrypoints==0.3
  - firebase==3.0.1
  - Flask==1.1.2
  - gcloud==0.18.3
  - googleapis-common-protos==1.53.0
  - gurobipy==9.1.2
  - httplib2==0.19.1
  - idna==2.10
  - imbalanced-learn==0.8.1
  - imblearn==0.0
  - import-ipynb==0.1.3
  - ipykernel==6.4.1
  - ipynb==0.5.1
  - ipython==7.28.0
  - ipython-genutils==0.2.0
  - itsdangerous==2.0.0
  - jedi==0.18.0
  - Jinja2==3.0.0
  - joblib==1.1.0
  - jsonschema==4.0.1
  - jupyter-client==7.0.6
  - jupyter-core==4.8.1
  - jwcrypto==0.9.1
  - kaggle==1.5.12
  - kiwisolver==1.3.1
  - MarkupSafe==2.0.0
  - matplotlib==3.4.2
  - matplotlib-inline==0.1.3
  - Naked==0.1.31
  - nbformat==5.1.3
  - nest-asyncio==1.5.1
  - numpy==1.20.2
  - oauth2client==4.1.3
  - pandas==1.2.3
  - parso==0.8.2
  - pickleshare==0.7.5
  - Pillow==8.2.0
  - prompt-toolkit==3.0.20
  - protobuf==3.17.3
  - pyasn1==0.4.8
  - pyasn1-modules==0.2.8
  - pycodestyle==2.7.0
  - pycparser==2.20
  - pycryptodome==3.10.1
  - Pygments==2.10.0
  - pyparsing==2.4.7
  - pyrsistent==0.18.0
  - python-dateutil==2.8.1
  - python-firebase==1.2
  - python-jwt==3.3.0
  - python-slugify==5.0.2
  - pytz==2021.1
  - pywin32==301
  - PyYAML==5.4.1
  - pyzmq==22.3.0
  - requests==2.25.1
  - requests-toolbelt==0.9.1
  - rsa==4.7.2
  - scikit-learn==1.0
  - scipy==1.7.1
  - seaborn==0.11.2
  - shellescape==3.8.1
  - six==1.15.0
  - sseclient==0.0.27
  - text-unidecode==1.3
  - threadpoolctl==3.0.0
  - toml==0.10.2
  - tornado==6.1
  - tqdm==4.60.0
  - traitlets==5.1.0
  - urllib3==1.26.4
  - wcwidth==0.2.5
  - Werkzeug==2.0.0
  - wrapt==1.12.1

### Usage:

In order to run a model, open the project directory ("user_behaviourdata") in VS Code.

- install the required dependencies.
- open and run the file "data_preprocessing.ipynb"
  - it imports the dataset
    - imports from google drive
    - if face 404 error
      - uncomment the code in next cell
      - imports from local "datasets/users implicit feedback"
  - cleans data
  - visualises data
  - it analysis the user behaviour.
  - it calculates the weights for individual layout.
  - normalizes the weights.
  - saves the final results in local directory "datasets/user-layouts ratings/normalized_data.csv"
- open and run the file "item_based_CB.ipynb"
  - it imports the csv file from
    - "datasets/users-layouts ratings/normalized_data.csv" or
    - drive
  - finds the similarity among users
  - finds the similarity among items
  - it saves the model in directory "Models/IBCF/item_item_weight_matrix"
  - it evaluates the item_based collaborative filtering model using Hold-Out and k-fold cross validation
  - measures the statistical and descision support accuracy metrics
- open and run the file "matrixFactorizationModel.ipynb"
  - it imports the csv from
    - "datasets/users-layouts ratings/normalized_data.csv" or
    - drive
  - trains the model using Hold-Out and k-fold cross validation
  - shows the training results of the models
  - it saves the model in directory "Model/matrixfactorization/"
    - following files are included:
      - user_factors.json
      - item_factors.json
      - user_bias.data
      - item_bias.data
      - avg.npy (average ratings or global bias)
  - imports the model files from "Model/matrixfactorization/"
  - validates the model using Hold-Out and k-fold cross validation
  - measure the statistical and descision support accuracy metrics

---

## Recommend Layouts

Flask app for layouts recommendations.

- before users' data collection flask app was developed
- recommends top layouts to cold start users based on existing users' rating
- directories contain all the necessary files require to build a flask app

### virtual environment settings

install virtualenv using

```
$ pip install virtualenv
```

Enable virtual enviornemnt:

```
$ .\Scripts\activate
```

### Required Libraries and packages to test the app

- requirements.txt defines required libraries/dependencies

### Usage

- datasets directory contains the normalized_data.csv as catalogue
- models directory contains the matrix factorization recommendation model
  - trained model is taken from the user behaviour data directory
- app.py file defined on root
  - defins @app.route
    - requires http method
    - user id as parameter is required, whom the layouts will be recommended
  - reads the "normalized_data.csv" from dataset
- recommender.py computes the recommendations
  - if user already exists in catalogue (normalized_data.csv)
    - makes recommendation by considering user's past behaviour
  - if user does not exist in catalogue (normalized_data.csv)
    - recommends layouts based on ratings given by other users
- send request and get response
  - http://127.0.0.1:5000/rows/+user_id
  - add user_id as parmeter
- pyvenv.cfd is virtual environment's configuration file

---

## Android Application

contains AUI_AndroidProject project root directory

### Environment settings

- dependencies are defined in Gradle Scripts
  - build.gradle project level:project file
  - build.gradle module level:app files
- all the libraries and dependencies will be installed automatically

### Usage

- test the app
  - install the app "APK/app-debug.apk"
  - or download from the link "https://download1641.mediafire.com/85nqw14rf8jg/gubsy3t0r2uxyln/app-debug
  - or use virtual android device from android
    - install the virtual device from AVD Manager in android studio
- package "com.example.AdaptiveUIInterface" contains business logic code
- "res" contains:
  - drawables (drawale resource files xml and images)
  - layouts (layout resource files in xml)
  - other folders are also important to successfully run the code in java
- Main activity is defined in the manifest/AndroidManifest.xml file
  - bottom and top bars are defined in the activity_main.xml
  - fragment_container hosts the 10 pre-designed layouts
    - each layout implements a recyclerview defined in .xml
      - open layouts and go to inflater to see the layout's xml
    - recycler view places the cartview
      - a cart view for each layout is designer
        - can be accessed from category adapter
        - category adapter places the movies' data on cartview
    - Movies' data is accessed from the IMDB open source API
      - to collect data background operations are performed in "MoviesDataSetRequestHandler.java"
      - "https://api.themoviedb.org/3/movie/popular?api_key=b780564d04479e16101f7701777d2d91&page="+pagenumber (get movies by page numbers)
  - at the start, all the layouts are accessible from the toolbar and bottom navbar
  - after generating small user behvioral data, Flask App is constructed to get more users' data (See Recommend Layouts below)
  - to use the app
    - Signup
    - SignIn
    - read the note before proceeding (which can be replaced for users' agreement collection)
    - Note: first time app might take time to proceed ahead from the dialogue of users' consent
