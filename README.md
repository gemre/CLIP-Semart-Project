# CLIP-Semart-Project

# CLIP-Semart-Project

## Project Overview
This project explores the robustness of the CLIP (Contrastive Language-Image Pre-training) model for artist attribution in artwork classification using the SemArt dataset. The study investigates how various image transformations affect CLIP's ability to correctly identify artists based on visual features.

## Dataset
The project uses the **SemArt dataset**, which contains:
- **19,244 artworks** with complete metadata
- 9 columns: IMAGE_FILE, DESCRIPTION, AUTHOR, TITLE, TECHNIQUE, DATE, TYPE, SCHOOL, TIMEFRAME
- Distribution across different artistic periods (TIMEFRAME)
- Multiple artistic schools (Italian School, Flemish School, etc.)
- Various artwork types (paintings, sculptures, etc.)

## Methodology
We conducted three main experiments to test CLIP's robustness under different image transformations:

### 1. Elastic Deformation Experiment
- Applied elastic distortions to artwork images
- Tested whether CLIP can maintain artist attribution despite geometric transformations
- Results stored in `elastic_results_df.csv`

### 2. Perspective Transformation Experiment  
- Applied perspective transformations to simulate different viewing angles
- Evaluated CLIP's invariance to viewpoint changes
- Results stored in `perspective_results_df.csv`

### 3. Grayscale Conversion Experiment
- Converted colored artworks to grayscale
- Assessed the importance of color information for artist attribution
- Results stored in `grayscale_results_df.csv`

## Key Results
Each experiment tracked:
- **Original prediction**: CLIP's predicted artist on original images
- **Original confidence**: Confidence score for the original prediction
- **Transformed prediction**: Predicted artist after transformation
- **Transformed confidence**: Confidence score after transformation
- **Still correct**: Boolean indicating if the prediction remained accurate

### Summary of Findings
The experiments reveal how different visual features contribute to CLIP's artist attribution capabilities:
- **Elastic deformations** impact geometric features
- **Perspective changes** test viewpoint invariance
- **Grayscale conversion** isolates the role of color vs. form

## Repository Structure
```
├── AI_Research_Semart.ipynb              # Research analysis notebook
├── Ai_project.ipynb                       # Main project notebook
├── Ai_project_perspective_experiments.ipynb  # Perspective transformation experiments
├── descriptive_statistics.ipynb           # Dataset statistical analysis
├── merge_dataset.ipynb                    # Dataset merging utilities
├── merge_dataset_updated.ipynb            # Updated dataset merging
├── semart_full.csv                        # Complete SemArt dataset
├── elastic_results_df.csv                 # Elastic deformation experiment results
├── perspective_results_df.csv             # Perspective transformation experiment results
├── grayscale_results_df.csv               # Grayscale conversion experiment results
└── README.md                              # This file
```

## Technologies Used
- **CLIP**: OpenAI's Contrastive Language-Image Pre-training model
- **Python**: Primary programming language
- **Jupyter Notebooks**: Interactive development and analysis
- **Pandas**: Data manipulation and analysis
- **Matplotlib**: Data visualization
- **Image Processing Libraries**: For applying transformations

## Usage
1. Clone this repository
2. Install required dependencies
3. Open the Jupyter notebooks to explore the experiments
4. Review the CSV files for detailed results

## Future Work
- Test additional transformation types
- Expand to more artists and artistic styles
- Compare CLIP's performance with other vision models
- Investigate the impact of training data on robustness

## Contributors
This project is part of AI research on computer vision models for art analysis.

## License
Please refer to the SemArt dataset license for data usage terms.
