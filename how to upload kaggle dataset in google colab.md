# Copy Paste this code at the beginning of your .ipynb notebook

## Prerequisites :  Go to your kaggle account page and select create new API token

### An json file will be downloaded in your computer

```
!pip install kaggle
```
### After the installation is completed, use !ls -a to check if you have a directory called .kaggle under the content, if not, make one:

```
!mkdir .kaggle
```

```
import json
token = {“username”:”YOUR-USER-NAME”,”key”:”SOMETHING-VERY-LONG”}
with open(‘/content/.kaggle/kaggle.json’, ‘w’) as file:
    json.dump(token, file)

```
```
!cp /content/.kaggle/kaggle.json ~/root/.kaggle/kaggle.json
```

**Then Run**

```
!kaggle config set -n path -v{/content}
```

**To Download Data**

* Go to the Kaggle competition page you would like to download data from , and browse to Data, I’m using Home Credit Default Risk competition as an example:
* Scroll down to the data section and click API button, it will copy the command automatically.
* Paste the command into Colab’s cell (don’t forget the exclamation mark). Add the -p to specify your path.

```
!kaggle competitions download -c home-credit-default-risk -p /content

```

**To unzip the files run the following command**
```
!unzip \*.zip
```
**Now your data is available to use. Try:**

```
import pandas as pd
d = pd.read_csv('application_train.csv')
d.head()

```
