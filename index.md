# Saisohan Shingade
sshingade@ucsd.edu

**Section:** D31, Ensemble of Agents | **Mentor:** Yoav Freund

**What is the most interesting topic covered in your domain this quarter?**  
Boosting, especially how AdaBoost turns many weak classifiers into a strong one by reweighting the examples it got wrong. Seeing it go from the voted perceptron and bagging (Breiman 1996) to Viola–Jones made it click: the same idea of combining simple rules drives a real-time face detector, where boosting picks a few useful Haar features out of thousands and a cascade throws out easy negatives early. It is very intersted to me how averaging as a concept can reduce noise enough to create a meaningful signal.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**  
The main direction is whale call classification: turn audio into spectrograms, pull features out of them (band energies, Haar-like box features over time and frequency), and train a boosted classifier to detect and label calls. Related directions if that goes faster than expected or doesn't pan out: (1) a Viola–Jones-style cascade on spectrograms, so quiet stretches get rejected cheaply and only likely calls reach the expensive stages; (2) testing how well a detector trained at one recording site or season transfers to another; (3) using boosting's confidence scores to flag uncertain clips for human labeling (active learning), since labeled whale audio is scarce.

**What is a potential change you'd make to the approach taken in your current Quarter 1 Project?**  
Our agents build classifiers by tuning knobs on face detection, with an LLM coordinator deciding what to try next. I'd make the search more disciplined: fix a held-out test set early and log every configuration, so the agents can't overfit to the validation data through repeated tries. I'd also compare the LLM coordinator against simple baselines like random search and Bayesian optimization, so we know whether the coordinator actually adds value or only adds cost.

**What other techniques would you be interested in using in your project?**  
Gradient boosting (XGBoost/LightGBM) as a stronger baseline than AdaBoost; small CNNs on spectrograms to compare learned features with hand-built ones; data augmentation for audio (time shifts, noise mixing, frequency masking); and calibration plus precision-recall analysis, since whale calls are rare and plain accuracy would be misleading.
