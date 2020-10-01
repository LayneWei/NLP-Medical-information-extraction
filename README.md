# UC Berkeley MEng Capstone Project

This project, combined with cTAKES (we assume that you have used cTAKES and have some basic understanding of how it works), is used for enable precision medicine and improving the working efficiency for medical NLP researchers. To summarize briefly, it's consist of three parts. 

#### 1.UserInterface
The first one is in the UserInterface Folder, which builds User Interface to display output of cTAKES added with some additional features: The comprehensive distribution of confidence score of the whole medical data, in which you can click on each datapoint to access more detailed information about that datapoint. Also in the main webpage, you can see the output of cTAKES in a organized way and a corresponding confidence score of that concept. When you click on the concept, all the reference sentence from original text from medical records where the medical concepts are extracted will appear on the page. By clicking on any of them, the user will be able to label the data as right or wrong in terms of the output of cTAKES.

#### 2.NLP Metrics
One important component of our project is the calculation of NLP metrics, the second one is the mechanism behind the calculation of NLP metrics, including BLEU Score, Cosine Similarity, Jaccard Similarity, Levenshtein Similarity, Elmo Score.

#### 3.Machine Learning Models
As mentioned in the UserInterface part, one of the ultimate goals is to display the confidence score to the users. Using the NLP metrics data calculated for each concept as X, the user labeld data as label y, we were able to train several machine learning models to predict the confidence score for each concept. These models include Logistic Regression, SGD Classifier, KNN Classifer as well as Random Forest, among which random forest has the best performance and we incorporate this machine learning model into our user interface for the confidence score prediction.

The way it works is that we calculated NLP metrics including BLUE Score, Cosine Similarity, Elmo, Jaccard Similarity, Levenshtein Similarity from the output of cTAKES as X for machine learning, and we label 1000 data manually as y. After the machine learning model has been trained, when there are new data, the model will predict the confidence score of new data based on the calculated NLP metrics of that datapoint. Afterwards, all the information will be displayed in the user interface and the user can keep continuing labeling the data for machine learning to improve system reliability so that there's a active learning and prediction loop.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.
We are working on deploying it to AWS to have more people access it.

### Prerequisites
Due to Github size constraints, we were unable to upload the complete Word2Vec model to Github.
After cloning the repository from Github, go to

```
https://drive.google.com/open?id=1AIeDjK9UlmhuMU3LNKZrzyKEh9ghm3aQ
```
And download the files to the directory
```
flaskr/cosine_model
```

### Installing

Run the command
```
pip install -e .
```
This will install the required dependencies.

Following this, on mac run the commands

```
$ export FLASK_APP=flaskr
$ export FLASK_ENV=development
$ flask run
```
on Windows cmd:
```
> set FLASK_APP=flaskr
> set FLASK_ENV=development
> flask run
```

It is quite likely that the program will be slow, as it runs a number of computationally intensive NLP tasks.
We are working on deploying the tool to AWS for more computational efficiency and to allow multiple people to access the tool and give feedback data, to create an exhaustive concept accuracy database.


## Running the tests

Explain how to run the automated tests for this system


## Deployment

Follow the [flask instructions](https://flask.palletsprojects.com/en/1.1.x/tutorial/deploy/) for details on how to deploy the UI to a production environment.

## Built With

* [Flask](https://flask.palletsprojects.com/en) - The web framework used

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Marcel Schaack** - *Initial work* - [MarcelSchaack](https://github.com/marcelschaack)
* **Lengning Wei** - *Initial work* - [LayneWei](https://github.com/LayneWei)
* **Chloe Kim** - *Initial work* - [ChloeKim](https://github.com/chloekim)

See also the list of [contributors](https://github.com/LayneWei/NLP-Project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Thank you to Gundolf Schenk and Gabriel Gomes for all your helpful adivse throughout the year.
* We also want to thank the Fung Institute and the Berkeley College of Engineering of helping us!
