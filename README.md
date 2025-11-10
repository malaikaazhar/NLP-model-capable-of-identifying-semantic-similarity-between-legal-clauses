Legal Clause Similarity using Siamese Neural Networks
1. Network Details

This project uses two Siamese neural network architectures for clause similarity detection:
BiLSTM-based and Attention-based encoders. Both networks share a common structure with two identical subnetworks that generate embeddings for clause pairs and a final dense layer that computes similarity.


• Embedding Dimension: 128
• LSTM Hidden Dimension: 64
• Dropout Rate: 0.3
• Vocabulary Size: 30,000 (TextVectorization layer)
• Sequence Length: 128 tokens
• Optimizer: Adam (learning rate = 0.001)
• Loss Function: Binary Crossentropy
• Activation Function (Output): Sigmoid
• Epochs: 5
• Early Stopping: patience = 2 (based on validation accuracy)

2. Dataset Splits

The dataset was built by combining multiple clause files, containing 'clause_text' and 'clause_type' columns.
Pairs were generated as follows:
- Positive pairs: Clauses of the same type (label = 1)
- Negative pairs: Clauses of different types (label = 0)


The dataset was split into:
• 70% Training set
• 15% Validation set
• 15% Test set


3. Performance Measures

Both models were evaluated using multiple classification metrics:
• Accuracy – overall correctness of classification
• Precision – proportion of correctly predicted similar clauses
• Recall – proportion of actual similar clauses identified
• F1-Score – harmonic mean of precision and recall
• ROC-AUC & PR-AUC – measure the ability to rank pairs correctly


Model	Accuracy	Precision	Recall	F1-Score	ROC-AUC	PR-AUC
BiLSTM Siamese	0.873	0.868	0.871	0.870	0.905	0.898
Attention Siamese	0.856	0.852	0.854	0.853	0.892	0.884
4. Performance Comparison

The BiLSTM Siamese model achieved slightly better performance than the Attention Siamese model in terms of accuracy and F1-score.
The Attention model, however, trained faster and demonstrated smoother convergence.

Overall, both architectures perform competitively, with BiLSTM showing marginally higher classification capability,
while the Attention model offers computational efficiency.

