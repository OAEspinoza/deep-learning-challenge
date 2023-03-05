# deep-learning-challenge
## Background
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With my knowledge of machine learning and neural networks, I used the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.
## Results
### Data Preparation
The following actions were performed to prepare the data:
- The EIN and NAME columns were dropped because they are neither targets nor features.
- The number of unique values for each column was calculated.
- For columns that have more than 10 unique values, the number of data points for each unique value was calculated.
- Data was split in training and testing sets.
- The target binary variable is "IS_SUCCESSFUL" (1=Yes, 0=No).
- The CLASSIFICATION variable was used for binning purposes.
- get_dummies was used to encode categorical varaibles.
### Compiling, Training, and Evaluation of the Model
Three layers were included. The number of input features was 46. The number of hidden nodes in each layer were as listed below:
- Hidden_nodes_layer1=80
- Hidden_nodes_layer2=30
- Hidden_nodes_layer3=1
- A total of 6,141 parameters were created 
- A callback was created to save the model's weights every five epochs. Results were saved in the "checkpoints" folder.
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

- Lastly, results were saved and exported to an HDF5 file (see "Content" folder)

#### Table 2
<table>
    <tr>
        <td>268/268 - 0s - 294ms/epoch - 1ms/step</td>
    </tr>
    <tr>
        <td>Loss: 0.5622002482414246</td>
    </tr>
    <tr>
        <td>Accuracy: 0.7293294668197632</td>
    </tr>
</table>

### Optimizing the Model
In the second trial, the column "NAME" was kept, and this resulted in an accuracy of 78%. Tables 3 and 4 show the model and results. Similar steps for data pre-processing, compiling, training, and evaluating the model were followed.
<br>

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
<table>
    <tr>
        <td>268/268 - 0s - 276ms/epoch - 1ms/step</td>
    </tr>
    <tr>
        <td>Loss: 0.4976328909397125</td>
    </tr>
    <tr>
        <td>Accuracy: 0.7870553731918335</td>
    </tr>
</table>


