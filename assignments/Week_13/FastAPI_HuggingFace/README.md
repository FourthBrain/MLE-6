<p align = "center" draggable=”false” ><img src="https://user-images.githubusercontent.com/37101144/161836199-fdb0219d-0361-4988-bf26-48b0fad160a3.png"
     width="200px"
     height="auto"/>
</p>



# <h1 align="center" id="heading">HuggingFace using FastAPI</h1>

For this session, our goal will be implement HuggingFace sentiment analysis using FastAPI, launch our local server, and hit the `docs` endpoint.

## HuggingFace && FastAPI
* Your endpoint should return to the user if the sentiment of the query is positive or negative (based off the query they provide).

1. First off pip install the needed libraries: `pip install transformers torch torchvision torchaudio`
2. Your code could look something like this:

```python
from transformers import pipeline
sentiment_model = pipeline("sentiment-analysis")

sentiment_query_sentence = get_random_comment(top_comments)
sentiment = sentiment_model(sentiment_query_sentence)
print(f"Sentiment test: {sentiment_query_sentence} == {sentiment})
```
But now you need to modify this in a way that can take in the query sentence and format a response to the user and return through FastAPI. It can be very close to this though!

3. FastAPI requires you to set a `Pydantic` model to make sure the request comes in formatted correctly. Let's make that:

```python
from pydantic import BaseModel

class PredictionRequest(BaseModel):
  query_string: str
```

4. Create a `post` endpoint with whatever name you like similar to this:

```python
@app.post("my-endpoint")
def my_endpoint(request: PredictionRequest):
  # YOUR CODE GOES HERE
```

5. Put your HuggingFace code into `main.py` and the logic within your `my_endpoint` function
6. Test that this works locally by running your server: `uvicorn main:app --port 8000` and navigate to your browser `localhost:8000/docs` to test it out.

## Resources
* https://fastapi.tiangolo.com/tutorial/first-steps/
* https://fastapi.tiangolo.com/tutorial/body/
