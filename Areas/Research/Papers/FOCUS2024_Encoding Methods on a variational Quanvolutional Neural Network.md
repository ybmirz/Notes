---
tags:
  - research-papers
---


**Preliminary Study: Enhanced Quantum Image Encoding in a Variational Quanvolutional Neural Network for Improved Image Classification**

Mirza Hizriyan Nubli Hidayat, Dr. Tan Chye Cheah [^1]

[^1] School of Computer Science, University of Nottingham Malaysia (hfymh3@nottingham.edu.my, chyecheah.tan@nottingham.edu.my)

**Abstract.** This paper explores the implementation of Enhanced Novel Enhanced Quantum Representation (ENEQR) and Enhanced Flexible Representation of Quantum Images (EFRQI) as encoding methods in a variational quanvolutional neural network (VQNN). These novel encoding methods aim to improve efficiency and accuracy of quantum image representation, and further could improve the classification performance of a VQNN. Experimental results demonstrate that EFRQI significantly reduces training time compared to FRQI, and ENEQR improves accuracy over NEQR. The findings of this study show an improved configuration for a VQNN. Another step towards practical applications for hybrid machine learning models.

**Keywords:** Quantum algorithm, Quantum computing, Quantum image encoding, Quanvolutional neural network, Hybrid quantum-classical models, Quantum machine learning

# 1 Introduction

As initially described by Feynman [1], the advent of quantum computing has opened new avenues for advancing classical computational tasks, including those in machine learning and image classification. Hybrid quantum-classical models, which integrate quantum computational elements with classical neural networks, have become a newer field of study, demonstrating potential benefits in terms of computational efficiency and model performance. The hybrid models, in the context of this work, hybrid quantum-classical convolutional neural networks (HQCCNNs), have shown promise in leveraging quantum circuits to enhance traditional convolutional processes. This integration is done at its convolutional layer, interchangeably described as the quanvolutional layer.
 While the integration of quantum circuits into classical neural networks has been extensively explored, there remains a significant potential for optimizing these models through improved quantum image encoding methods. It’s often described that machine learning models are as effective as the data they are trained on. Similarly, quantum image encoding is crucial for efficiently representing classical image data in quantum states, which directly impacts the performance of these hybrid models.

This paper presents a novel contribution by implementing two advanced quantum image encoding methods – Enhanced Novel Enhanced Quantum Representation (ENEQR) and Enhanced Flexible Representation of Quantum Images (EFRQI) – in a variational quanvolutional model. A variational quanvolutional model slightly differs in approach by applying a learnable quantum circuit in the quanvolutional layer by updating the gate rotation parameters based on the weights described. This paper focuses on applying novel encoding methods on the variational model, and we aim to demonstrate the effectiveness of these encoding methods in improving the accuracy and efficiency of image classification tasks.
 The primary objective of this research is to evaluate the performance enhancements brought forward by ENEQR and EFRQI encoding methods when integrated into a variational HQCCNN framework. Our experimental results show that these encoding methods significantly improve the model performance compared to previously implemented encoding techniques, highlighting their potential to push the boundaries of quantum machine learning.

# 2 Background and Related Works

## 2.1 Hybrid Quantum-Classical (Quanvolutional) Neural Networks

Quanvolutional models utilize quantum circuits to perform complex transformations on the input image data, which are then processed by classical neural network layers. The concept of utilizing parametrized quantum circuits to replace the convolution layer of a CNN was first proposed by [2]. In their implementation, a random layer of single and two qubit rotation gates were used to replicate the convolution of a CNN. It should be noted that the rotation parameters of these qubit operations were fixed and initialized randomly at the random layer. Additionally, the images were encoded based on a threshold value of which the gray scale pixel intensity value was measured and represented in the initial qubit states of |0⟩ and |1⟩. This model was then evaluated on the MNIST dataset among a traditional CNN model and a CNN with additional non-linearities. The paper's results indicate that among the hybrid model generally have a higher test set accuracy and maintain faster training time compared to classical CNNs. However, this does not explicitly determine a definite quantum advantage, and further research would be needed to determine if observed improvements in accuracy and training speed are a direct result of quantum transformations.
 Improving on top of this initial model, [4] provided a variational approach towards the implementation of this hybrid model. As an additional novelty for improvement, the paper proposes a variational quanvolution layer by updating the parameters of the quantum gate operations in the random circuit similar to the weight updates of the classical components in a CNN.
 In essence, backpropagation updates are applied to the quantum gate parameters in the random circuit layer as well as the other classical components. The experimental results of this paper indicate that models with trainable circuits show lower error values on training and validation sets compared to models with fixed parameters in quantum circuits. In its experimentation, the paper described [2]’s implementation with a basic *threshold encoding.* It thus proceeded and thus proceeded to experiment and implement hybrid models with other quantum image encoding methods such as the Flexible Representation of Quantum Images (FRQI) and Novel Enhanced Quantum Representation (NEQR). These two methods were initially proposed by [3] and [5], respectively. The experimentation was also done on the MNIST dataset.
 One of the limitations of this paper, was the training time of the models being extensively high due to the measurements required by the higher amount of qubit operations representing the images in the encoding methods – in comparison to the simple threshold encoding. The experimental results do show, however, that with a better encoding method, the hybrid models provide better training and validation accuracy. Both of the proposed hybrid models, in [2] and [4], have demonstrated the feasibility and possible advantage of quanvolutional models in an image classification task.

There are other various notable methods of implementing the quantum aspect of a quanvolutional neural network, such as a quantum graph CNN model, where [6] utilized quantum parametrized circuits for graph-level classification tasks – instead of an image classification task. [7] continues to investigate the features proposed by [2] and improves upon the training strategy using different topologies, sizes and depths of filters, instead of applying a trainable quanvolutional layer. They proceed to suggest an efficient configuration for the *baseline* quanvolutional neural network, utilizing the fixed parameterized random quantum circuit layer. It seems to be commonplace in this research space to look towards improving existing hybrid models, either by applying or experimenting with a new approach for classification.

## 2.2 Quantum Image Encoding Methods

A critical component of the described hybrid models is the method used to encode the classical image data into quantum states. Quantum image encoding involves representing an image as a high-dimensional quantum state, described by amplitudes or coefficients in its vector representation. Each pixel’s intensity value is encoded into the amplitudes and relative phases of the quantum state’s components, in the form of a quantum state .
 It is common knowledge that a machine learning model is as effective and good as its training data. Hence, an effective quantum image encoding is essential for preserving the image information while making them amenable for the quanvolutional layer. As previously described, [4] has implemented FRQI and NEQR as the quantum image encoding methods for their variational model. Since this variational approach shows the most promise to further advance these models, we’ll describe and breakdown these encoding methods for the context of this paper. Both encoding methods are applied for a gray scale image. Similarly, this study will investigate other quantum image encodings to be implemented on a variational quanvolutional neural network. Below describes the encoding methods briefly, with their strengths and novelties.

One of the simplest methods is Threshold Encoding, which encodes each pixel as either |0⟩ or |1⟩, depending on whether its value is above or below a certain threshold. While straightforward to implement, this method may suffer from significant information loss, making it less suitable for detailed image representation. Its simplicity makes it a great initial step in experimenting with quantum image encoding. As previously described, this encoding method was proposed alongside the model in [2].

The Flexible Representation of Quantum Image (FRQI) proposed by [3] in 2011. It encodes pixel values as angles in the qubit representation by using controlled y-rotation parameterized by . FRQI requires qubits to encode an image, given that the pixel value essentially is represented by the probability of a qubit to flip either to |0⟩ or |1⟩. This method enables efficient quantum image storage and manipulation but can be limited by precision and sensitivity to quantum noise when applied on quantum hardware.

The Novel Enhanced Quantum Representation (NEQR) proposed by [5] in 2013. This method directly represents pixel values as binary strings in the basis states. This approach ensures high fidelity and preserves most of the image information but requires a significant number of qubits. The state is prepared by applying the Hadamard and -CNOT gates. NEQR uses about qubits, where represents the grayscale value’s bit depth.

To address the high quantum cost associated with NEQR, the Enhanced NEQR (ENEQR) was proposed by [8], in 2021. It incorporates an auxiliary qubit to reduce the number of controlled-NOT (CNOT) gates needed for encoding pixel positions, improving scalability and efficiency while maintaining high fidelity. ENEQR requires qubits to represent an image.

The Enhanced FRQI (EFRQI) proposed by [8], in 2021. This method improves upon FRQI by using a partial negation operator (RX gate) to set the qubit amplitudes. This method reduces the time complexity associated with preparing quantum states and allows for more precise encoding of grayscale values, potentially providing faster training time and improved accuracy. Since it is in essence, still FRQI, this method requires qubits to represent the image.

Finally, the Bitplane Representation of Quantum Images (BRQI) proposed by [9], represents an image by decomposing it into several bit planes, with each plane encoded separately in quantum states. This method allows for more nuanced manipulation of image details, potentially enhancing tasks like edge detection and texture analysis. BRQI requires qubits, where is the number of bit planes. Its ability to manage image details at a more granular level allows possibly to hold more information of an image in its encoding.

# 3 Methodology

## 3.1 Research Approach

This research aims to enhance the results of the previously established quanvolutional models, specifically focusing on the improvements outlined in [4]. In this study, we explore the potential enhancements that ENEQR and EFRQI, as encoding methods, would provide to the performance of variational quanvolutional neural networks. These two encoding methods were chosen amongst others due to the direct focus of finding an improvement to [4]. The primary research question addressed is: would the implementation of these enhanced encoding methods (ENEQR and EFRQI) provide a measurable improvement over the previously implemented NEQR and FRQI methods in a variational quanvolutional neural network?

The ENEQR encoding method optimizes the encoding process of NEQR by introducing an auxiliary qubit, thereby reducing the number of controlled-NOT (CNOT) gates required. This study implements the ENEQR encoding method following the pseudocode below.

**Figure 1.** High-level Pseudocode to implement EFRQI

**Algorithm 1** ENEQR Quantum Image Representation

1: Initialize quantum register *ψ*0 = 0⊗(2*n*+*q*+1)

2: Apply *H*⊗2*n* ⊗ *I*⊗(*q*+1) to *ψ*0 to prepare the position state

3: **for** each pixel position (*Y, X*) **do**

4: Calculate the binary representation *bq*−1 *...b*0 of the gray value

5: Set the auxiliary qubit *aux* using a 2*n*-CNOT gate controlled by *Y X*

6: **for** *i* = 0 to *q* − 1 **do**

7: Apply CNOT gate controlled by *aux* to flip *bi* if necessary

8: **end for**

9: Reset *aux* for reuse

10: **end for**

11: Measure the quantum register to retrieve the image

Based on the above pseudocode, the ENEQR encoding method is first initialized with enough qubits to accommodate the binary encoding of pixel values. The quantum circuit initialization consists of applying the Hadamard gates to all the wires in the circuit. Iterating through each pixel to retrieve the exact gray intensity value, converting it to an 8-bit binary string. With this string, each bit is iterated and for each bit that is a ‘1’, a CNOT gate is applied with the positional qubit being the control wire.

The EFRQI encoding method extends the FRQI method by using a partial negation operator (RX gate) to set qubit amplitudes more efficiently, which reduces time complexity and possibly improves classification precision. The general process of encoding is divided into two steps, storing the pixel position into an intermediate state and completing by applying a sub-operation consisting of operations to set the gray value for every pixel in the image. The position of the pixels are set into the intermediate state by using the single qubit gates such as identity gate *I* and Hadamard gate *H*. This study implements this encoding method following the pseudocodes below.

**Figure 2.** High-level Pseudocode to implement EFRQI

**Algorithm 3** EFRQI Quantum Image Representation

1: Initialize quantum register *ψ*0 = 0⊗(2*n*+1)

2: Apply *H*⊗2*n* ⊗ *I* to *ψ*0 to prepare the position state

3: **for** each pixel position (*Y,X*) **do**

4: Calculate the gray value *v* of pixel (*Y,X*)

5: Apply *RXv* ⊗ *Y X* controlled by position state *Y X*

6: **end for**

7: Measure the quantum register to retrieve the image

Based on the above pseudocode, this implementation encodes the required qubit amounts, with a loop through all the pixel coordinates of *x* and *y*, the gray value is retrieved and is used to compute or scale the angle according to it. The qubits were initialized into a state based on the pixel’s given amplitude using a *QubitStateVector* function. The computed parameterized RX gate is then applied to the qubit at the corresponding position. This step effectively encodes the gray value into the amplitude of the qubits’ quantum state.

## 3.3 Dataset and Implementation

The experiments utilize the MNIST dataset of handwritten digits [13], resized to a 14x14 pixels for computational efficiency. The exact amount for the input dataset includes 10,000 training images, a validation set of 200 images and 1,000 test images. The code implementation of this study was directly implemented on top of the open-source code provided by [4]. Following the original implementation, the novel encoding methods are applied for the 2x2 quanvolutional filter of the input image. Following the variational implementation approach, the encoding circuit representing the image is connected to the random trainable circuit in the quanvolutional layer, and the output of the quanvolutional layer is a measurement of the connected parameterized quantum circuit as a tensor vector, utilized for the remaining classical components of the hybrid model. The model contains a single quanvolutional layer with a single pooling layer, finalized in a fully connected layer to perform the final classification.
 The models are implemented using PyTorch for its classical components and Pennylane and Qiskit used for the quantum circuits. As previously discussed, the two novel encoding methods were implemented onto a variational quanvolutional neural network, where the quantum circuit parameters are trained alongside the classical network parameters.

## 3.4 Training and Evaluation

The training and evaluation process of this study was designed to specifically test whether the two novel encoding methods, ENEQR and EFRQI, could provide measurable improvements over the traditional NEQR and FRQI methods on a variational quanvolutional neural network. The experimental setup includes models employed the cross-entropy loss function and the Adam optimizer, commonly used for its adaptive learning rate capabilities. This optimizer was also used in the previous implementation since the random circuit parameters were implemented as an updating weight in the optimizer. Each epoch consisted of 100 training steps followed by 50 validation steps, with models trained for 50 epochs. During each step, batches of 32 images were processed, and gradients were calculated and used to update the model parameters, with quantum circuit parameters updated using the parameter shift rule.

To evaluate the effectiveness of the encoding methods, we employ common key performance metrics for model evaluation. The classification, both training and validation, accuracy was the primary metric, indicating the model’s proportion of correctly classifying images. Computational efficiency was assessed by measuring training time, as well as considering the number of qubits and quantum gates required. Additionally, the convergence rate was monitored by tracking the reduction in training loss over epochs, with faster convergence indicating more efficient learning and better model generalization.

The experiments were structured to directly compare the performance of EFRQI vs FRQI, and ENEQR vs NEQR. For each comparison, the training images were encoded using the respective methods, and two separate models were trained and evaluated. This involved encoding the images with FRQI and EFRQI for one set of comparisons, and NEQR and ENEQR for another. The performance metrics consist of training accuracy, training loss, validation accuracy and validation loss. Each model’s metrics are compared with one another to determine the relative improvements provided by the enhanced encoding methods.

# 4 Results and Disscussion

## 4.1 Overview of Result

This section provides an overview of the training time and accuracy metrics for all the encoding methods tested. Our focus in this section is on the performance improvements offered by all encoding methods in terms of both training time and accuracy. Below is an overview of the results to provide an encompassing perspective on the enhancements of the encoding methods. It should be kept in mind that all the models were trained under the same configurations and experimental setup on the same training machine. Threshold encoding was implemented and recorded as a control and baseline encoding method.

**Table 1.** Training time of variational quanvolutional neural networks based on encoding method.

| Encoding Method | Mean Training Time per Step | Mean Total Training Time |
| --- | --- | --- |
| Threshold | 1.420s | 1.9727 hours |
| FRQI | 3.012s | 4.1843 hours |
| NEQR | 2.939s | 4.0823 hours |
| EFRQI | 1.933s | 2.6842 hours |
| ENEQR | 3.218s | 4.4706 hours |

The training time for each encoding method was measured and compared. As shown in Table 1, EFRQI demonstrated a significant improvement over FRQI in terms of training time, with a mean total training time of 2.6842 hours compared to FRQI’s 4.18433 hours. However, ENEQR took longer to train, with a mean total training time of 4.4706 hours compared to NEQR’s 4.08 hours. EFRQI’s faster training time per step also showed to be faster than FRQI’s, which potentially shows the faster time complexity of the encoding directly impacting the training time of the model, even in a minute scale. Unsurprisingly, the threshold encoding took the least amount of time to train due to its simplistic nature, aligning with the results of previous implementations. Using that as a baseline, the EFRQI encoding method shows promising result as an efficient encoding method to be used in a variational quanvolutional neural network.

**Table 2.** Training and validation accuracy of variational quanvolutional neural network based on encoding method.

| Encoding Method | Training Accuracy | | | Validation Accuracy | | |
| --- | --- | --- | --- | --- | --- | --- |
| Mean | Max | Variance | Mean | Max | Variance |
| Threshold | 0.787 | 0.835 | 0.000738 | 0.787 | 0.88 | 0.00283 |
| FRQI | 0.794 | 0.885 | 0.001592 | 0.815 | 0.89 | 0.00195 |
| NEQR | 0.769 | 0.860 | 0.002129 | 0.778 | 0.87 | 0.00245 |
| EFRQI | 0.866 | 0.915 | 0.000796 | 0.847 | 0.91 | 0.00131 |
| ENEQR | 0.868 | 0.930 | 0.001182 | 0.853 | 0.90 | 0.00080 |

Table 2 provides a summary of the mean, maximum and variance of training and validation accuracy for all encoding methods. The mean accuracy reflects the average performance of the quanvolutional model during the training and validation phases. Higher mean accuracy indicates better overall performance. The maximum accuracy indicates the best performance achieved by the variational model given an encoding method, at any point during training and validation. Higher maximum accuracy suggests that the model can possibly achieve very high performance under optimal conditions. Variance measures the variability in accuracy, showing consistency of the model’s performance.

EFRQI shows a notable improvement in both training and validation accuracy over FRQI. EFRQI achieved a mean training accuracy of 0.866, and a mean validation accuracy of 0.847, significantly higher than FRQI’s mean training and validation accuracies of 0.794 and 0.815, respectively. Conversely, ENEQR, while taking longer to train, still shows improved accuracy metrics over NEQR. The low variance in most implementations of the models shows consistent and stable performance, hence having reliable results. ENEQR showed a mean training accuracy of 0.868 and a mean validation accuracy of 0.853, both higher than NEQR’s mean accuracies of 0.769 and 0.778. Lower variance of the performance results was shown throughout the novel encoding methods, noting its reliability in learning. For a further investigation into possible improvements these enhanced encoding methods provide towards the variational model’s performance, the following sections will describe the performance changes over time between two rival encoding methods, EFRQI vs FRQI and ENEQR vs NEQR.

## 4.2 EFRQI vs. FRQI

The EFRQI encoding method is expected to provide a more robust and adaptable encoding strategy compared to FRQI. This enhancement in the encoding specifically provides an improvement in time complexity in encoding the information whilst providing the same robust image information capture as FRQI.

Based on the experiment result, the EFRQI encoding applied on the variational model shows similar performance with the FRQI, though with a relatively better resulting maximum training and validation accuracy. Although not a huge performance improvement performance, the slight increase in performance suggests that utilizing FRQI allowed for greater capture of nuances and complexities of the training data as representation. In the validation phase, EFRQI seems to consistently maintain a higher accuracy compared to FRQI. Based on the training validation loss graph, both EFRQI and FRQI have difficulty stabilizing the variational model’s learning process. This notes that EFRQI does not provide improvements in stabilizing the model’s learning, though provides a slight increase in learning accuracy. Nevertheless, recalling the training time decrease EFRQI provides over FRQI and this slight increase in accuracy proves an enhancement provided by EFRQI allowing the variational quanvolutional neural network to continue learning at a slightly higher training and validation accuracy – with a faster training time.

## 4.3 ENEQR vs. NEQR

The ENEQR encoding method implemented on the variational quanvolutional model aims to provide an improved representation of the input quantum images, by enhancing NEQR’s efficiency and effectiveness, yielding better performance metrics in both training and validation. Additionally, ENEQR is expected to optimize the quantum state space usage, which could make the encoding process more efficient. This could further lead to less information loss during encoding, quanvolution and pooling.

Key observations from the experiment result show a few trends. Both NEQR and ENEQR models show a similar trend in training accuracy, but ENEQR consistently performs better, particularly in the latter half of the epochs. ENEQR further exhibits a significantly lower training loss than NEQR, which indicates its superior capability in encoding and learning from training set. ENEQR seems to allow the model to converge to (and start at) a higher accuracy compared to NEQR. During the validation phase, ENEQR outperforms NEQR in terms of validation accuracy throughout most epochs. The validation loss of ENEQR also shows to be very stable across epochs, which could point to much better generalization capabilities provided by the enhancement. The reduced fluctuation in validation loss suggests that ENEQR is far less likely to be affected by overfitting compared to NEQR.

# 5 Conclusion

The application of novel quantum encoding methods, EFRQI and ENEQR, on a variational quanvolutional neural network yielded promising results in terms of training efficiency and model accuracy. Compared to the previously used FRQI encoding, the EFRQI method demonstrated a significant reduction in total training time, with a mean of 2.68 hours versus 4.18 hours for FRQI. This improvement in training efficiency can be attributed to the reduced time complexity of EFRQI's encoding process, which utilizes a partial negation operator (RX gate) to set qubit amplitudes more efficiently. By accelerating the encoding step, the model could train more rapidly, optimizing resource utilization.

In addition to enhanced training speed, the EFRQI model exhibited a slight improvement in accuracy, with a mean training accuracy of 0.866 and validation accuracy of 0.847, compared to 0.794 and 0.815, respectively, for the FRQI model. The lower variance in EFRQI's performance metrics suggests a more robust and reliable encoding that captures input image information more effectively during training.

While the ENEQR encoding did not improve training time compared to the NEQR method (4.47 hours versus 4.082 hours), it significantly boosted accuracy metrics. The mean training accuracy for ENEQR was 0.868, with a validation accuracy of 0.853, outperforming NEQR's 0.769 and 0.778, respectively. This accuracy enhancement can be attributed to ENEQR's higher fidelity encoding, which incorporates an auxiliary qubit to reduce the number of CNOT gates, thereby providing better precision in representing grayscale values and improving the representation of input images in the quanvolutional layer.

Despite longer training times, the ENEQR model exhibited lower variance in accuracy, suggesting more reliable and consistent performance, similar to EFRQI's results. This reliability is crucial for applications where stability and precision in learning are paramount, demonstrating that ENEQR's encoding method enhances the learning capabilities of a variational quanvolutional neural network. Additionally, ENEQR's encoding appears to provide more stable learning for the variational model compared to NEQR in this study's experimentation.

The observed improvements offered by EFRQI and ENEQR highlight the potential of utilizing advanced quantum encoding methods to significantly enhance the performance of quanvolutional neural networks. By reducing training time and increasing accuracy, these novel methods make the machine learning model more practical and efficient, facilitating broader adoption across various applications.

The findings from this study open avenues for future research. Further optimization and development of advanced quantum image encoding methods could be explored and applied to variational quanvolutional neural networks, potentially yielding additional reductions in training time and accuracy improvements. The proposed EFRQI and ENEQR encoded models could be tested on more complex and diverse datasets, providing insights into their robustness and generalizability across different data types, including higher resolution images or real-world practical grayscale imaging. Moreover, implementing these encoding methods and the quanvolutional layer on actual quantum hardware, rather than simulators used in this study, could provide practical insights into their real-world performance and feasibility. This step is crucial for transitioning from theoretical and simulated results to practical applications in quantum machine learning.

In conclusion, this study has implemented two new encoding methods, EFRQI and ENEQR, providing significant improvements over their previously implemented encoding methods on a variational quanvolutional neural network. The method enhanced both the efficiency and accuracy of their respective models allowing for more potential practicality of these hybrid models for image classification. These advancements show a step forward in quantum machine learning, with potential applications in various domains where data processing and classification are critical. Future works could build on these findings to continue improving the capabilities and applications of hybrid quantum-classical machine learning models. Improving and applying these hybrid models on more practical real-world data may one day provide a reason for quantum machine learning to surpass and further be utilized over classical machine learning.

# References

[1] R. P. Feynman, “Simulating physics with computers,” *International Journal of Theoretical Physics*, vol. 21, no. 6–7, pp. 467–488, 1982, doi: 10.1007/bf02650179.

[2] M. Henderson, S. Shakya, S. Pradhan, and T. Cook, “Quanvolutional neural networks: powering image recognition with quantum circuits,” *Quantum Mach Intell*, vol. 2, no. 1, pp. 1–9, 2020, doi: 10.1007/s42484-020-00012-y.

[3] P. Q. Le, F. Dong, and K. Hirota, “A flexible representation of quantum images for polynomial preparation, image compression, and processing operations,” *Quantum Inf Process*, vol. 10, no. 1, pp. 63–84, 2010, doi: 10.1007/s11128-010-0177-y.

[4] D. Mattern, D. Martyniuk, H. Willems, F. Bergmann, and A. Paschke, “Variational Quanvolutional Neural Networks with enhanced image encoding,” 2021.

[5] Y. Zhang, K. Lu, Y. Gao, and M. Wang, “NEQR: a novel enhanced quantum representation of digital images,” *Quantum Inf Process*, vol. 12, no. 8, pp. 2833–2860, 2013, doi: 10.1007/s11128-013-0567-z.

[6] J. Zheng, Q. Gao, and Y. Lu, “Quantum Graph Convolutional Neural Networks,” 2021, doi: 10.23919/ccc52363.2021.9550372.

[7] P. Atchade-Adelomou and G. Alonso-Linaje, “Quantum-enhanced filter: QFilter,” *Soft comput*, vol. 26, no. 15, pp. 7167–7174, 2022, doi: 10.1007/s00500-022-07190-w.

[8] N. Nasr, A. Younes, and A. Elsayed, “Efficient representations of digital images on quantum computers,” *Multimed Tools Appl*, vol. 80, no. 25, pp. 34019–34034, 2021, doi: 10.1007/s11042-021-11355-4.

[9] H.-S. Li, X. Chen, H. Xia, Y. Liang, and Z. Zhou, “A Quantum Image Representation Based on Bitplanes,” *IEEE Access*, vol. 6, pp. 62396–62404, 2018, doi: 10.1109/access.2018.2871691.

[10] H. Li, P. Fan, H. Xia, H. Peng, and S. Song, “Quantum Implementation Circuits of Quantum Signal Representation and Type Conversion,” *IEEE Transactions on Circuits and Systems I-regular Papers*, vol. 66, no. 1, pp. 341–354, 2019, doi: 10.1109/tcsi.2018.2853655.

[11] X. Liu, D. Xiao, W. Huang, and C. Liu, “Quantum Block Image Encryption Based on Arnold Transform and Sine Chaotification Model,” vol. 7, pp. 57188–57199, 2019, doi: 10.1109/access.2019.2914184.

[12] J. Sang, S. Wang, and Q. Li, “A novel quantum representation of color digital images,” *Quantum Inf Process*, vol. 16, no. 2, 2016, doi: 10.1007/s11128-016-1463-0.

[13] L. Deng, “The MNIST Database of Handwritten Digit Images for Machine Learning Research [Best of the Web],” *IEEE Signal Process Mag*, vol. 29, no. 6, pp. 141–142, 2012, doi: 10.1109/msp.2012.2211477.

