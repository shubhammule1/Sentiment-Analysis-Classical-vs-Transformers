## 🤗 Transformer Fine-Tuning Comparison (DistilBERT)

| Metric                    | Full Fine-Tuning | LoRA Fine-Tuning |
|---------------------------|------------------|------------------|
| Training Time (minutes)   | 14.92            | **4.84**  |
| Validation Accuracy       | **0.8911**  | 0.8711 |
| Validation F1 Score       | **0.8906**  | 0.8732 |
| Trainable Parameters      | 66,955,010       | **739,586**  |
| Total Parameters          | 66,955,010       | 67,694,596 |



## ⚡ Efficiency Gains (LoRA vs Full Fine-Tuning)

| Metric                         | Improvement |
|--------------------------------|------------|
| Training Speedup               | **3.08× faster**  |
| Trainable Parameter Reduction  | **98.90% fewer parameters**  |
