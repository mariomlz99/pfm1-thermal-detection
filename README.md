# iccas_submission_supp
**ICCAS Submission Supplementary Material**

This repository provides supplementary material for the ICCAS submission, specifically showcasing the parameters obtained through optimization.

## Optimized Parameters

The following table presents the symbolic representation and optimization range for each parameter found in the YAML configuration files. These parameters were tuned using Optuna, and are grouped according to their role in the system:

## Optimized Parameters

| YAML Parameter                    | Symbol        | Range         |
|----------------------------------|---------------|---------------|
| `HOT_PIXEL_PERCENTAGE`           | `P_hot`       | [0.1, 0.5]     |
| `MIN_BLOB_SIZE`                  | `A_min`       | [15, 40]       |
| `AVG_THERMAL_GRADIENT_THRESHOLD`| `T_G`         | [60, 80]       |
| `MAX_TRACKING_DISTANCE`          | `D_max`       | [30, 60]       |
| `MIN_STRENGTH_THRESHOLD`         | `S_min`       | [0.4, 0.95]    |
| `STRENGTH_DECAY`                 | `D_S`         | [0.4, 0.9]     |
| `PERSISTENCE_THRESHOLD`          | `T_pers`      | [0.2, 1.0]     |
| `initial_valid_strength`         | `S_valid_init`| [0.7, 1.0]     |
| `initial_invalid_strength`       | `S_invalid_init`| [0.3, 0.8]   |
| `matched_decay_base`            | `M_base`      | [0.6, 0.8]     |
| `matched_decay_bonus`           | `M_bonus`     | [0.2, 0.5]     |
| `unmatched_decay_base`          | `U_base`      | [0.4, 0.7]     |
| `unmatched_decay_bonus`         | `U_bonus`     | [0.1, 0.4]     |
| `VALIDITY_MARGIN_RATIO`         | `V_margin`    | [0.5, 0.9]     |
| `gradient_decay_factor`         | `D_grad`      | [0.0, 1.0]     |
| `fallback_search_radius`        | `R_fb`        | [10, 40]       |

Additionally:
- `train_score`: training score achieved by the configuration.
- `best_trial_number`: the index of the best trial found by Optuna during hyperparameter search.
- `beta_for_score`: the value of β used in the FBeta score evaluation.

## Configuration Folders

Each folder contains a full YAML configuration corresponding to a specific training/validation and optimization objective:

- `TrainT1_ValT2_F1Score`: Trained on Track 1, validated on Track 2, optimized for F1 score.
- `TrainT1_ValT2_FBetaScore`: Trained on Track 1, validated on Track 2, optimized for FBeta score.
- `TrainT2_ValT1_F1Score`: Trained on Track 2, validated on Track 1, optimized for F1 score.
- `TrainT2_ValT1_FBetaScore`: Trained on Track 2, validated on Track 1, optimized for FBeta score.

## Fixed Parameters (Manually Tuned)

The following parameters were set manually based on camera-track setup, environmental conditions, and sensor characteristics:

- \( S_{\text{erode}} = 4 \)
- \( S_{\text{dilate}} = 3 \)
- \( r_{\text{ring}} = 5 \)
- \( T_{\text{hist}} = 50 \)
- \( N_H = 2 \)
- \( N_G = 3 \)

These values were chosen empirically:
- Morphological kernel sizes \( S_{\text{erode}} \), \( S_{\text{dilate}} \), and ring radius \( r_{\text{ring}} \) were set based on the nominal camera–track distance.
- Thermal-related parameters \( T_{\text{hist}} \), \( N_H \), and \( N_G \) were fixed according to ambient conditions and sensor refresh rate.
