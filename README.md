# hERG-LTN: A New Paradigm for hERG Cardiotoxicity Prediction Using Neuro-Symbolic and Generative AI
![hERG-LTN Banner](git-imgs/herg-ltn-banner.jpg)

---

## Abstract
Assessing adverse drug reactions (ADRs) during drug development is essential for ensuring the safety of new compounds. The blockade of the Ether-a-go-go-related gene (hERG) channel plays a critical role in cardiac repolarization. Computational predictions of hERG inhibition can help foresee drug safety, but current data-driven approaches have limitations. Therefore, a new paradigm that bridges the gap between data and knowledge offers an alternative for advancing precision pharmacogenomics in assessing hERG cardiotoxicity.

This study aims to develop a reasoning-based, *in silico*, robust model for predicting drug-induced hERG inhibition, thereby facilitating new drug development by reducing time and cost, supporting downstream *in vitro* and *in vivo* testing. 

In this study, we constructed a new cohort, **UnihERG_DB**, by sourcing data from ChEMBL, PubChem, BindingDB, GTP, hERG Karim's, and hERG Blocker's bioactivity databases. The final dataset comprises **20,409 structures** represented as SMILES (Simplified Molecular Input Line Entry System), labeled as hERG blockers (**IC50 < 10 µM**) or non-hERG blockers (**IC50 ≥ 10 µM**). Molecular features were extracted using **Morgan** and **CDK fingerprints**. Furthermore, we explored embedding feature computation using cutting-edge Large Language Models, including **NVIDIA MegaMolBart**, **LLaMA 3.2**, **Gemini**, and **DeepSeek**. 

Finally, we utilized the **Logic Tensor Network (LTN)**, an advanced AI framework, to train and develop the hERG predictive model. Model performance was evaluated using two benchmarks: **External Test-1** and **hERG-70**. The Logic Tensor Network (LTN) outperformed several models, including **CardioTox**, **M-PNN**, **DeepHIT**, **CardPred**, **OCHEM Predictor-II**, **Pred-hERG 4.2**, **Random Forest**, and **Gradient Boosting**. 

- On the **External Test-1** dataset, LTN achieved an **accuracy of 0.931**, a **specificity of 0.928**, and a **sensitivity of 0.933**.  
- On the **hERG-70** benchmark, LTN achieved an **accuracy (ACC) of 0.827**, a **specificity (SPE) of 0.890**, and a **correct classification rate (CCR) of 0.833**.

Overall, the Neuro-Symbolic AI approach sets a new standard for hERG-related cardiotoxicity assessment, yielding competitive results with current state-of-the-art (SOTA) models, and highlights its potential for advancing precision pharmacogenomics in drug discovery and development.
### Dataset
data card: [Download](https://drive.google.com/drive/folders/1joG-nNPFJ12TAsu2nesSI6ctimB8hU_7?usp=sharing)


### Architecture
![hERG-LTN Banner](git-imgs/ltn-arch.png)

### Result
* **Externel Positive Testset-I**
![hERG-LTN Banner](git-imgs/ex-pos-test1.png)

* **Externel hERG-70 Testset-II**
![hERG-LTN Banner](git-imgs/ex-h70-test2.png)

---

## License

This repository — code, notebooks, and the trained checkpoints in `Model-Weights/` — is licensed under the **MIT License**. See the `LICENSE` file in this repository.

That means you may use, copy, modify, and redistribute the contents, including the model weights, including in commercial products, provided you keep the copyright and license notice. The contents are provided "as is", without warranty of any kind.

This is research software for hERG cardiotoxicity prediction. It is **not** a medical device and is **not** intended for clinical or diagnostic use.

## Model weights — verify before use

The checkpoints in `Model-Weights/` are inference-only published weights. Verify the file you have before using it — do not rely on file size or input width alone.

`hERG-UniChemDB-Morgan.keras` and `hERG-UniChemDB-LLAMA.keras` are both 2048 inputs wide and both 148,406 bytes, so they cannot be distinguished by size or input width.

| Checkpoint | SHA-256 |
|---|---|
| `hERG-UniChemDB-Morgan.keras` | `517ad2c3814b87b3e18bc1c20a5984df5bc19b9212e0eb7f3a520bfb5cf13f43` |
| `hERG-UniChemDB-LLAMA.keras` | `ea3bb0978a5a173f685a544b53fe3807406a63b24c712b79dfdb2a2f3a6a9aa0` |

Check with: `sha256sum Model-Weights/hERG-UniChemDB-Morgan.keras`
