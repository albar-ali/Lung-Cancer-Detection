Dataset Refinement & Balancing

In this project, I focused on a balanced binary classification task to ensure maximum model reliability.

    Initial State: The raw dataset was imbalanced with Class 1 (561 samples) and Class 2 (416 samples).

    Balancing Technique: I performed Manual Undersampling on the majority class.

    Final Split: I selected 416 samples from each class, resulting in a perfectly balanced dataset of 832 total images.

    Impact: This approach eliminated class bias, allowing the model to focus purely on feature extraction rather than being skewed by sample frequency.


Experimental Framework (Model Benchmarking)

I evaluated the performance of three different deep learning architectures on this balanced dataset:

    EfficientNetB0 (V1 & V2): * Tested for its specialized scaling and efficiency.

        Although V2 showed faster convergence, it was more sensitive to hyperparameter tuning in this specific medical context.

    ResNet50 (Final Architecture): * Why ResNet? The residual connections (skip connections) proved highly effective at vanishing gradient problems during the fine-tuning of medical textures.

        Optimization: Used a custom head with 256 neurons, Dropout (0.5), and a dynamic Learning Rate scheduler.

Class 3 was excluded from this phase of the study to maintain a high-confidence balanced baseline. Future iterations will involve oversampling techniques to integrate the minority class (120 samples) into a multiclass framework.

In previous attempt my dataset was small , and model had two many layers,
so model was not learning. My data gen technique was also wrong(because it was a medical dataset) 
then i also increase the value of Dropout. 
then i also make some of convlution unfreeze and train the model
for 50 epochs
