# Lip-Reading
Deep Learning Model that can LIP READ using Python and Tensorflow

In light of the existing landscape, this project advocates for the adoption of LipNet—a groundbreaking end-to-end model that pioneers sentence-level sequence prediction for visual speech recognition. Unlike prior methodologies, LipNet efficiently processes sequences of images and yields output distributions over sequences of tokens. This project proposes an advanced lip reading model that combines 3D Convolutional Neural Networks (CNNs) and Gated Recurrent Units (GRUs) to improve the accuracy and robustness of lip reading The project's approach involves leveraging the spatio-temporal characteristics of lip motion using 3D CNNs. This allows the model to analyze sequential frames of lip movements and capture both spatial and temporal features simultaneously. The GRU component is employed to learn long-term dependencies and capture temporal dynamics in the lip movement sequences.

<b>How it works?</b>

-The LipNet architecture operates through a meticulously designed sequence of operations.

-It begins with a series of three stages, each involving spatiotemporal convolutions, channel-wise dropout, and spatial max-pooling.

-This initial stage extracts crucial information from the input, encapsulating essential features.

-The architecture introduces two Bidirectional Gated Recurrent Units (BI-GRUs), a pivotal element in the process.

-These Bi-GRUs facilitate the effective aggregation of outputs from the earlier spatiotemporal convolutions.

-Following this, each time-step undergoes a linear transformation.

-Subsequently, a softmax operation covers a vocabulary expanded to encompass the CTC blank symbol.

-The architecture's learning process is driven by the application of the Connectionist Temporal Classification (CTC) loss.

-Throughout the architecture, the Rectifled Linear Unit (ReLU) serves as the activation function in all layers.

-This consistent choice of activation function contributes to the model's efficiency and performance.

-The orchestrated sequence of operations culminates in the LipNet architecture's proficiency in lip reading tasks.

<b>Dataset</b>

We employ the GRID corpus for training due to its sentence-level nature and extensive dataset. The sentences are structured using a straightforward grammar pattern: command(4) + color(4) + preposition(4) + letter(25) + digit(10)+ adverb(4). Each number indicates the available word choices within the corresponding word category. These categories encompass (bin, lay, place, set), (blue, green, red, white), (at, by, in, with), (AZ)(W), (zero, nine), and (again, now, please, soon), resulting in a pool of 64,000 potential sentences. For instance, exemplars from this dataset Include 'set blue by A four please' and 'place red at C zero again. Model training was conducted on the first 450 videos of speaker one.

<b>Architecture</b>
LipNet architecture. A sequence of T frames is used as input, and is processed by 3 layers of STCNN, each followed by a spatial max-pooling layer. The features extracted are processed by 2 Bi-GRUs; each time-step of the GRU output is processed by a linear layer and a softmax. This end-to-end model is trained with CTC.
![alt text](https://images.deepai.org/converted-papers/1611.01599/x1.png)

<b>Model Perfomance metrics</b>
-Word Error Rate = 4.8%
-Sentence accuracy = 95.2%
-Training Videos = 450
-Trainable parameters = 8471924
-Vocabulary tokens = 41








Reference - LIPNET: END-TO-END SENTENCE-LEVEL LIPREADING
Yannis M. Assael, Brendan Shillingford, Shimon Whiteson & Nando de Freitas
Department of Computer Science, University of Oxford, Oxford, UK
Google DeepMind, London, UK CIFAR, Canada
