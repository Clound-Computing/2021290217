This repository contains the source code and data for ACL 2021 paper: "How is BERT surprised? Layerwise detection of linguistic anomalies" by Bai Li, Zining Zhu, Guillaume Thomas, Yang Xu, and Frank Rudzicz.

Dependencies:\
The project was developed with the following library versions. Running with other versions may crash or produce incorrect results.\
Python 3.7.5\
CUDA Version: 11.0\
torch==1.7.1\
transformers==4.5.1\
numpy==1.19.0\
pandas==0.25.3\
scikit-learn==0.22

Setup Instructions\
1.Clone this repo: https://github.com/Clound-Computing/2021290217.git \
2.Download BNC Baby (4m word sample) from this link and extract into data/bnc/ \
3.Run BNC preprocessing script: python scripts/process_bnc.py --bnc_dir=data/bnc/download/Texts --to=data/bnc.pkl \
4.Add Blimp（file） to data（file） \
 \
GMM experiments on BLiMP         \
PYTHONPATH=. time python scripts/blimp_anomaly.py \
  --bnc_path=data/bnc.pkl \
  --blimp_path=data/blimp/data/ \
  --out=blimp_result

  Surprisal gap experiments    \
PYTHONPATH=. time python scripts/run_surprisal_gaps.py \
  --bnc_path=data/bnc.pkl \
  --out=surprisal_gaps  
 \
  Accuracy scores   \
PYTHONPATH=. time python scripts/run_accuracy.py \
  --model_name=roberta-base \
  --anomaly_model=gmm
\

Citation：\
Li, B., Zhu, Z., Thomas, G., Xu, Y., and Rudzicz, F. (2021) How is BERT surprised? Layerwise detection of linguistic anomalies. In Proceedings of the 59th Annual Meeting of the Association for Computational Linguistics (ACL).
