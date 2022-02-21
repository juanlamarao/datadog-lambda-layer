# datadog-lambda-layer

## Instalation
### AWS Lambda Layer
<text>
<upload_file>

### Binding Layer to function
<text>

### Usage
1. Import the layer to your coode
```python
import datadog as datadog
```
2. Create an object following [datadog documentation](https://docs.datadoghq.com/serverless/custom_metrics/#custom-metrics-sample-code)
```python
import time
import random

datadogObject = {
	"series": [
		{
      			#metric name in datadog
			"metric": "test.python.lambda",
			"points": [
				[
        				#time in epoch
					int(time.time()),
        				#metric value (getting a random number for this example)
					random.randrange(51)
				]
			]
		}
	]
}
```
3. Send metric through the layer function
```python
res = datadog.send_metric(datadogObject)
print(res)
```
