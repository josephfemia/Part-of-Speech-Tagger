# Part of Speech Tagging


## Dependencies


This project was made using a ```requirements.txt``` for keeping track of dependencies.


First you should create a virutalenv for the project. To do this, cd into the directory and run the command:
```
python -m venv /path/to/new/virtual/environment
```
Next you need to activate your virtual environment by running:
```
source <path/to/venv>/bin/activate
```
* Note: the above command is specific to bash/zsh. Check out [python documentation](https://docs.python.org/3/library/venv.html) for your specific shell and platform.
Finally, to install the necessary dependencies run:
```
pip install -r requirements.txt
```


## Prerequisites


The model contained within the jupyter notebook utilizes the brown dataset that is contained within this repository. The file ```brown-universal.txt``` contains the sentences and associated parts of speech, while ```tags-universal.txt``` contains a list of all possible parts of speech contained within the ```brown-universal.txt``` file.


## Notebook Summary


In this notebook, I create two types of speech taggers: a MFC (Most Frequent Counter) Tagger and a HMM (Hidden Markov Model). The MFC Tagger is a baseline that simply uses the most common associated part of speech for a given word. This model is used as a baseline to compare our HMM against. The goal is to show that our HMM improves upon this baseline. I feel that this [TowardsDataScience](https://towardsdatascience.com/markov-and-hidden-markov-model-3eec42298d75) article does a great job of describing what a HMM is if you are unfamiliar. I utilize the [Pomegranate](https://pomegranate.readthedocs.io/en/latest/) library to help make the HMM. I then created a wrapper around this model that accepts a dataset and calculates all of the necessary emission and transition probabilities to initialize the model. I then compared the accuracy between the MFC Tagger and the HMM and saw an improvement of approximately 3% on the testing dataset.


## Future Improvements


There are still some improvements that could be made to this project.
* One thing that could be interesting to look at is the improvement of building a RNN (Recurrent Neural Network) to predict the part of speech and comparing the accuracy to that of the MFC Tagger and the HMM. My hypothesis would be that the RNN would outperform both models. My reasoning for this hypothesis is that going from the MFC Tagger to the HMM increased the model complexity, and we saw an improvement in the modeling performance on the testing dataset. I believe this to remain true when increasing the model complexity from a HMM to a RNN.
* As with most projects, the bigger the dataset, the better the model will be able to perform in unseen situations. Thus, one area to look into would be incorporating multiple datasets together from the [NLTK](https://www.nltk.org/) package. A full list of the [NLTK Corpora](https://www.nltk.org/nltk_data/) can be viewed [here](https://www.nltk.org/nltk_data/).