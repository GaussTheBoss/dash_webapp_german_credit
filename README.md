# Dash App Demo - German Credit Model

This project shows how a webapp developped in Dash (Python), can serve as an interface for interacting with a pre-trained model.

![Dash Webapp](webapp.PNG?raw=true "Dash Webapp")

The Dataset is the German Credit Dataset. The trained model can be found [here](https://github.com/GaussTheBoss/german_credit_python).

How the app works:

 - The input field is the `ID` (integer from 0 to 999).
 - On updated `ID`, the corresponding record is fetched from the dataset, and displayed in a 1-row table.
 - On clicking `Submit For Scoring`, the record (loan application details) is sent to the pre-trained model for inferencing.
 - The model (logistic regression) returns, along with the inputs, a `probability_of_default` as well as a `prediction`: `Default` or `Pay-Off`.
 - In addition, the app find the closest matches to the input record in the historical dataset, by computing the number of matching fields, sorting in descending order, and displaying the top 5 matches in the second table.
 - The `Save Data` button, when predictions have been made, can be used to download the data displayed on screen.
 - The rating slider and feedback text box are for demo purposes only. Interacting with them does not produce any actionable results. In a PROD environment, rating and feedback are typically logged, along with the prediction, into a database.

## Running Locally

To run this model locally, create a new Python 3.8.3 virtual environment
(such as with `pyenv`). Then, use the following command to update `pip`
and `setuptools`:

```
python3 -m pip install --upgrade setuptools
python3 -m pip install --upgrade pip
```

Then, install the required libraries:

```
python3 -m pip install -r requirements.txt
```

The main source code is contained in `app.py`. To run, execute

```
python3 app.py
```

By default, the app will be hosted locally on `http://127.0.0.1:8050/`
