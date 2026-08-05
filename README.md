# Perchv2_Retraining_Modular_Machine_Learning_Pipeline

This massive set of code should (hopefully, as of current I cannot test the re-training of epoch2 seeding due to data constraints), be able to re-train Perchv2 classifiers to better detect a specific species of interest! Make sure you have a lot of true positives and negatives ready as clips in folders (the program will walk you through)
You do not need to have anything labelled, just the clips ready - I have tried to make this very long and complicated process as obvious as possible with notes in separate code blocks throughout!

Everything you will need is discussed in the code as you go, so run one block at a time and read through carefully! I have made this as user-friendly as possible throughout so hopefully my instructions in the code are clear enough as to what each section is doing. See below for what the model can do for you (make sure it is right for your project before you get too far in); and what you will need to get started (this is also brought up during the code as comments in their own blocks as to what is needed when)! Hopefully everything makes sense for you, good luck and message me if you need any assistance understanding as you go!

# This model can:
1. Link to XenoCanto (you will need an account to supply the code with an API key - which it will temporary store for that session, so if you re-launch you will need to copy and paste it back in again)
2. Launch a review window on Gradio (a separate website link which you will be able to open directly when supplied), which is secured with a one-time session password (again, this resets each launch to keep data secure)
3. Automatically link reviewed clip labels into a usable csv without the user needing to ever deal with spreadsheet nightmares!
4. Perchv2 embedding generation automatically; with leakage-aware source grouping
5. Model training and threshold selection (which can be easily changed based on the data quality)
6. Trimmed-clip classification, as well as labelled challenge-set evaluation
7. Streaming hour-long recording scanning for detections (ideal for use in an array - especially CARACALs)
8. Candidate selection by the user with hard-negative reviews taking place again on the Gradio separate window to save the tagging mess again!
9. I've also incorporated incremental re-training (currently unable to test this section due to my own data constraints, but the skeleton at least will be there)
10. An optional independent calibration module if you are getting too many false positives etc.
11. Finally release packaging and reproducibility hashes if you wish to use the model you have built as a part of a wider pipeline (I am making one right now with my de-noiser and clip extractor into CARACAL array detection mapping for the full audio propagation pipeline)

# What you will need to make your model
1. A species of interest
2. A XenoCanto account
3. True positives clipped and manually identified from your data (as many as possible for training)
4. True negatives clipped and manually identified from your data (again, as many as possible for training)
5. Independent true negatives and positives for later re-training and verification (make sure to keep this set separate)
6. Some raw source-hours for hard-negative mining later
7. (Optional) An independent calibration set if you wish to have probabilities rather than scores (which is the default of the system but can be corrected for near the end of the code process)
8. A final untouched test set for the very end of the process (which you may wish to manually review after your model has run, to see if it is working how you would like it to!)
9. Several hours of time to go through the tagging process (I have streamlined this as much as possible to make it nice and fast in comparison to standard tagging methods!)
10. Patience!
