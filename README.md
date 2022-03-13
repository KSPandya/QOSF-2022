# QOSF-2022
Solution to QOSF 2022 screening task (COHORT 5)

In this file, I have submitted my solution to Task 2 for the screening. The problem was to encode and classify the given dataset using various encoding strategies and ansatz in the variational circuit. Here, I have considered the following Embeddings and  Layers ( using Pennylane) - Amplitude Embedding, Angle Embedding , Basis Embedding(to selected columns), IQP4 Embedding and some hybrid Embedding techniques(combining multiple embeddings in a single strategy), followed by BasicEntanglerLayers, StronglyEntanglingLayers and RandomLayers. 

Train data - mock_train_set.csv  &&
Test data - mock_test_set.csv

Properties - 
1. Total  size of train dataset - 300,5  (Last column denotes classes)
2. Total size of test dataset  - 120,5
3. Train data was further split into training set and validation set (0.15 * Total size of train dataset)
4. Train features size - 255,4 
5. Validation features size - 45,4 
6. Number of iterations used in training - 100
7. Batch size used - 15
8. Column vectors have been normalized.
9. All opeartions performed for 1 layer and 4 layers of the arcitecture.

The results obtained are - 
![image](https://user-images.githubusercontent.com/101512789/158073827-bd1ac9a2-3f0e-46fb-9daf-ce7d590f534c.png)
1. Overall, the best combination of encoding and choosing good ansatz in this case has been achieved using mix of `Angle and Amplitude Embedding`, which gave the test accuracy of `1.0` in the simplest case with only 1 Basic entanglement layer. This can be because the circuit has been perfectly fit by training and validation data. Even other strategies of this combination gave nearly perfect results.  All amplitude embedding can also be said to be partially successful as it also gives values close to  `0.9` in few cases.
2. However, the combination with `Basis embedding` and `IQP4` haven't shown any great results. These results can be improved further by trying various other layers, parameters,etc.
3. Some other techniques like `QAOAEmbedding`, `SimplifiedTwoDesign`, etc. haven't been considered to keep the structure simple and thorough.
