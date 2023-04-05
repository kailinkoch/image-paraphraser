## Image Paraphraser

*Premise: can you use a generative image model to paraphrase a caption?*

There are many approaches to paraphrasing, but with the rise of text to image models, I was curious if these models could be used as a paraphraser.

**Models**
I used 2 existing models.
1. DeepAI's [text2img API](https://deepai.org/machine-learning-model/text2img). This model takes a caption as an input and generates 4 images based on the caption
2. Show and Tell neural image captioner ([Vinyals et al 2015](https://arxiv.org/pdf/1411.4555.pdf))

**Process**
1. Input a caption
2. Generate images
4. Generate a caption for the image
5. Generate a new image based off the "paraphrased" caption
6. Generate a final caption for the new image
7. Measure how much the captions have shifted from the original

**Example Results**

<img width="604" alt="Screen Shot 2022-10-30 at 9 48 39 AM" src="https://user-images.githubusercontent.com/68975515/198890809-e1a3fca6-d065-4e12-9acd-e47dd4492353.png">



**Observations**
* The image model outperforms the relatively simple caption model, and so you can see the images gradually shift to reflect the caption's content.
* It's interesting how the caption model (which was not trained on generated images) struggles on the more unusual images.
* An interesting next step could include training a caption model using generated images or re-trying this experiment with more conventional prompts

## Update!
I've posted an update [here](https://github.com/kailinkoch/data-sci-notebooks/blob/main/blip%20image%20paraphraser.ipynb) with the results using a new and improved caption model, BLIP. It is definitely producing more descriptive captions, but still gets distracted by other elements of the images. Below are the results on the original starting images and new images.

<img width="559" alt="Screen Shot 2023-04-04 at 8 30 48 PM" src="https://user-images.githubusercontent.com/68975515/229974310-d56e06af-da00-43e1-984f-3f8a91e8486b.png">

<img width="556" alt="Screen Shot 2023-04-04 at 8 31 10 PM" src="https://user-images.githubusercontent.com/68975515/229974300-207ed059-1258-44b7-aa47-0144803470da.png">


