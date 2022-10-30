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
