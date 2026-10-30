# Pen / Pencil / Eraser Classifier
Pen / Pencil / Eraser image classification using MobileNetV2 in Google Colab (Team 4, ML Workshop).

## Results
- Total valid images: 240 (80 per class)
- Image size: 224 x 224
- Model: MobileNetV2 (transfer learning)
- Split: 80% training (192), 20% testing (48)
- Test accuracy: 91.67%
- Most confused classes: pen predicted as pencil (3 of 15 pens)
- Proposed improvement: add real photos of pens and pencils from different angles and backgrounds

## Confusion matrix
| Actual / Predicted | eraser | pen | pencil |
|---|---|---|---|
| eraser | 13 | 1 | 0 |
| pen | 0 | 12 | 3 |
| pencil | 0 | 0 | 19 |

## Files
- Colab notebook (.ipynb)
- Trained model (.keras)
- labels.txt (class order: eraser, pen, pencil)
- requirements.txt
-    - dataset_small.zip (240 images from internet searches, 80 per class, resized to 224 px)
     - ## Reflection

1. **Traditional programming vs machine learning:** In traditional programming we write the rules. In machine learning the model learns the rules from examples.
2. **Supervised learning:** Training a model on data that already has correct labels (pen, pencil, eraser).
3. **Why labeled images:** The model needs the correct answer for each image to learn, and we need labels to check its predictions.
4. **Consistent dimensions:** The model expects the same input size every time, so all images were resized to 224 x 224.
5. **Flattening:** Turning an image's pixel grid into one long list of numbers. MobileNetV2 handles the image shape itself, so I did not flatten manually.
6. **Dividing by 255:** Pixel values (0 to 255) are scaled to a small range so training is stable. Mine are scaled to -1 to 1 for MobileNetV2.
7. **Train/test split:** Training data teaches the model and test data checks it on unseen images (80% / 20%).
8. **What an SVM does:** It finds a boundary that separates the classes. I used MobileNetV2 transfer learning instead.
9. **What test accuracy tells us:** The share of unseen images predicted correctly: 91.67% for my model.
10. **How the confusion matrix helps:** It shows which classes get mixed up. In mine, 3 pens were predicted as pencils.
11. **Good on test images, poor on live photos:** Live photos differ in background, lighting and angle from the training images.
12. **Improvements:** More varied images, my own photos, more epochs, and fine-tuning the model.
13. **Consistent preprocessing:** The model only works if new images are prepared exactly like the training images.
14. **Not tuning on the test set repeatedly:** The test score would become over-optimistic, so a separate validation set should be used for tuning.
