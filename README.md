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
