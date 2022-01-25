<h1 align="center">Welcome to Winfreds-API</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.1-blue.svg?cacheSeconds=2592000" />
  <a href="https://www.gnu.org/licenses/gpl-3.0.en.html" target="_blank">
    <img alt="License: GPL--3.0" src="https://img.shields.io/badge/License-GPL--3.0-yellow.svg" />
  </a>
</p>

> An API based off of Infermedica's Symptom API for better usage on our Android App, Api using HTTP requests



## Install

Clone the repo:

```sh
https://github.com/Oang/Api.git
```

Intsall the requirements:

```sh
pip install -r requirements.txt
```

## Usage

First, an Infermedica App ID and API key is required which can be obtained [here](https://developer.infermedica.com/)

In [keys.py](change the following lines to your App ID and API key

```Python
APP_ID = 'Infermedica App ID here'
API_KEY = 'Infermedica API key here'
```

**This API must be hosted either hosted locally or using a Hosting Website, [Heroku](https://www.heroku.com/) is reccomended**

The API had 2 endpoints: `/symptoms` and `/diagnosis`

The `/symptoms` endpoint is a GET request that returns a JSON list of key-value symptom pairs 

```
https://YOUR_URL_HERE/symptoms
```

The `/diagnosis` endpoint is a POST request that will return a JSON List of possible diagnosis from the given information.

The following is required in the POST request:

```
gender (given at birth)
age
symptoms (Infermedica symptom ids are required)
```
Symptom IDs can be found [here](https://developer.infermedica.com/docs/v3/available-symptoms)

Sample request:

```https://YOUR_URL_HERE/diagnosis ```

Request Body:

```JSON
{
    "gender": "male",
    "age": 20,
    "symptoms": [
        "s_102",
        "s_715"
    ]
}
```
Response Body should look similar to this:

```JSON
{
    "conditions": [
        {
            "name": "Common cold",
            "probability": 33.879999999999995
        }
    ]
}
```
The name contains the medical condition, in this case ```Common Cold``` and the probability is a percentage in this case ```33.88%```

## Authors

👤 **Philemon Olang**
* Github: [Philemon OLang - @Oang](https://github.com/Oang)


## Show your support

Give a ⭐️ if this project helped you!

## 📝 License

Copyright © 2020-2021 
This project is [GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) licensed.

