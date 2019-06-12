# Pre-trained Models

*Note*: Make sure the last layer in Keras model definition is the Softmax activation layer, *i.e.* model.layers[-2].output is the logits and model.layers[-1].output is the softmax activation, because some attack algorithms require the logits output.

## Dataset: ImageNet (ILSVRC)

| Model Name | # Trainable Parameters  | Top-1 Accuracy   |  Top-5 Accuracy |
|------------|-------------------------|------------------|-----------------|
| MobileNet  |  4,231,976              |     0.68360      |  0.88250        |
|Inception v3| 23,817,352              |  0.76276         |     0.93032     |


