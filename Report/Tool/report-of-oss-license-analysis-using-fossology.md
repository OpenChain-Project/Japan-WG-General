# OSS license analysis using FOSSology to verify license in each file

## reported by Yuki Machida (translated by Hiro Fukuchi)

original (Japanese): 
https://qiita.com/machida-yuki/items/8738961fa3133296d4c7

## Operating environment

Note: Only the following environment has been verified.

| component        | version  |
|:------------|:-------------|
| license-coverage-grader | 41baaa4 |
| Python | 2.7.12 |
| FOSSology | 3.4.0  |
| SPDX | 2.1 |
| SPDX License List | 2.6 |
| Git | 2.17.1 |
| Google Chrome | 70.0.3538.77  |
| LibreOffice | 6.0.3.2 |
| Ubuntu Desktop 日本語 Remix	 |  18.04 |



## Procedure

Prerequisite: 
Ubuntu Desktop Japanese Remix is installed.
Basic setting of enviroment is completed.


### installing license-converage-grader


```
$ sudo apt update
$ sudo apt install git python-pip
$ sudo -EH pip install --upgrade pip
```

```
$ git clone https://github.com/spdx/license-coverage-grader.git
$ cd license-coverage-grader/
$ sudo -EH pip install --editable .
```

### Analyzing source code, generating SDPX file



### generating license list for each file


```
$ python -s <path to the directory of license-coverage-grader>/license-coverage-grader/spdx_scanner.py findutils-4.2.31.spdx > findutils-4.2.31.csv
```


### verifying licenses


## Note





