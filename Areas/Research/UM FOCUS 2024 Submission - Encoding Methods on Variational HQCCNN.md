---
aliases:
  - first paper
description: Overview of my submission on encoding methods
tags:
  - research-notes
---
 > Note: I love the fact that markdown has now become mainstream. As Kepano said ["companies that don't understand the importance of plain text is doomed"](https://x.com/kepano/status/1867655795522863330?s=12)  . The submission of the paper was added to this note through a plugin built around this idea.
 
My first ever submission of a research work, through a *professional* session, haha. The submission presents an implementation I played around with, using enhanced encoding methods for a variational (learning) quanvolutional (hybrid quantum-classical convolutions) neural network framework. 

Link to paper: [[UM FOCUS 2024 Submission - Encoding Methods on Variational HQCCNN]]

The study demonstrated improvements in efficiency and accuracy compared to traditional encoding methods, with EFRQI reducing training time by approximately 36% compared to FRQI, several limitations should be noted. The research scope is intentionally specialized, focusing exclusively on grayscale MNIST data at reduced resolution (14x14 pixels) which *highly likely* limits the broader applicability.

I disliked the idea of publishing this initially, due to the **really** limited applicability and practicality of this research - but seeing other research work often being a very limited and marginal progress in their respective field. 

[//]: Relate this to the note and observation of what it means to research, and minimal or marginal research. 

Going back to the study:
Of particular interest is the unexpected increase in training time for ENEQR compared to NEQR, potentially due to auxiliary qubit overhead in quantum simulation environments. This raises important questions about the method's efficiency when implemented on actual quantum hardware. While ENEQR achieved higher accuracy metrics (mean training accuracy of 0.868 vs NEQR's 0.769), the practical implications of this improvement must be weighed against the computational overhead.

The research consciously builds upon previous variational model implementations rather than exploring alternative encoding methods like BRQI, prioritizing direct enhancement of established techniques over broader exploration. This focused approach, while yielding meaningful improvements, leaves significant avenues for future investigation, particularly regarding generalization to higher-resolution images and diverse datasets.

The entire submission of the paper is based on my general experimentation (playing around) with a variational hybrid model for some image classification tasks, submitted for my [[Individual Dissertation - B.Sc. in Computer Science (University of Nottingham Malaysia)|bachelor's degree dissertation]]

