# An Implement of [TrinityRCL: Multi-Granular and Code-Level Root Cause Localization Using Multiple Types of Telemetry Data in Microservice Systems]("https://ieeexplore.ieee.org/document/10034937")

## Getting Started

### Pip
```bash
pip install -r requirements.txt
```

### Code Running

```bash
python main.py
```

## Result

|Dataset|Top@1|Top@3|Top@5|
|:-:|:-:|:-:|:-:|
|AIopsChallenge22||||

## Running on your own dataset

### Write Your Dataset

Write your dataset class like `AIops22Dataset`

The dataset need things as follow:
```
r"""
the shapes of data ytrues:
[
    "service1",
    "service2",
    ...
]
the shapes of data yentrys:
[
    "service1",
    "service2",
    ...
]
the shapes of data like:
[
    {
        "fault": {
            "host1" : {
                "fault1": [# time series data #]
            },
            ...
        },
        "hmetric": {
            "host1": {
                "metric1": [# time series data #]
            }
        },
        "smetric": {
            "service1": [# time series data #]
        },
        "trace": {
            "service1": {
                "service2": fail_rate(float) // service1 -fail rate-> service2
                ...
            }
        },
        "deploy": {
            "service1": "host1",
            ...
        },
    },
    {
        ...
    },
    ...
]
"""
```

### Add Your Config

add your config like `aiops22.yaml`

### Finally

Then just use your dataset as well as config and run!

