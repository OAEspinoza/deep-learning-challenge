# deep-learning-challenge
## Background
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With my knowledge of machine learning and neural networks, I used the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.
## Results
### Data Preparation
The following actions were performed to prepare the data:
- The EIN and NAME columns were dropped because they are neither targets nor features.
- Data was split in training and testing sets.
- The target binary variable is "IS_SUCCESSFUL" (1=Yes, 0=No).
- The CLASSIFICATION variable was used for binning purposes.
- get_dummies was used to encode categorical varaibles.
### Compiling, Training, and Evaluation of the Model
Three layers were included. The number of input features was 45. The number of hidden nodes in each layer were as listed below:
- Hidden_nodes_layer1=80
- Hidden_nodes_layer2=30
- Hidden_nodes_layer3=1
- A total of 6,141 parameters were created 
- The accuracy of the model was 72.7%, slightly below the target of 75%.
Tables 1 and 2 below show a partial view of the model and its outputs.

#### Table 1
<table>
    <tr>
        <td>Model: &quot;sequential&quot;</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td> Layer (type)               </td>
        <td> Output Shape              </td>
        <td>Param #   </td>
    </tr>
    <tr>
        <td> dense (Dense)</td>
        <td>(None, 80)</td>
        <td>3760</td>
    </tr>
    <tr>
        <td> dense_1 (Dense)</td>
        <td>(None, 30)</td>
        <td>2430</td>
    </tr>
    <tr>
        <td> dense_2 (Dense)</td>
        <td>(None, 1)</td>
        <td>31</td>
    </tr>
</table>

Total params: 6,221<br>
Trainable params: 6,221<br>
Non-trainable params: 0<br>
Number of input features:  46<br>
<br>
#### Table 2
________
268/268 - 0s - 226ms/epoch - 845us/step<br>
Loss: 0.5613420009613037<br>Accuracy: 0.7315452098846436
________


### Optimizing the Model
In the second trial, the column "NAME" was kept, and this resulted in an accuracy of 78%. Tables 3 and 4 show the model and results.

#### Table 3
<table>
    <tr>
        <td>Model: &quot;sequential_1&quot;</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td> Layer (type)               </td>
        <td> Output Shape              </td>
        <td>Param #   </td>
    </tr>
    <tr>
        <td> dense (Dense)</td>
        <td>(None, 80)</td>
        <td>36000</td>
    </tr>
    <tr>
        <td> dense_1 (Dense)</td>
        <td>(None, 30)</td>
        <td>2430</td>
    </tr>
    <tr>
        <td> dense_2 (Dense)</td>
        <td>(None, 1)</td>
        <td>31</td>
    </tr>
</table>
Total params: 38,461<br>
Trainable params: 38,461<br>
Non-trainable params: 0<br>
Number of input features:  449<br>
<br>

#### Table 4
________
268/268 - 0s - 243ms/epoch - 908us/step<br>
Loss: 0.491421103477478<br>Accuracy: 0.7848396301269531
________


