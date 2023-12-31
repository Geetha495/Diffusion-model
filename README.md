# Diffusion-model

# Denoising Diffusion Probabilistic Model (DDPM) for Image Generation

This repository contains the implementation of denoising diffusion model for image generation. 
## Files:

1. **diffusion.ipynb:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1hxVmxgzttsle-mGP5z9UHZcgNZqg9TXP?usp=sharing)
   - This Jupyter Notebook file contains the implementation of the diffusion model for image generation.
   - The model is trained on a one-bedroom image from the LSUN bedroom dataset.
   - It includes visualizations of both the forward and reverse processes of the diffusion model.

2. **evaluator.py:**
   - This Python script provides evaluation metrics for comparing images.
   - Metrics include FID (Fréchet Inception Distance), precision, and recall.
   - The script is designed to be run on two batches of images: a reference batch from the LSUN bedroom dataset and a sample batch generated from the diffusion model.

## Instructions:

### Running the Diffusion Model:

1. Open and run the `diffusion.ipynb` Jupyter Notebook using your preferred environment.
2. The notebook contains detailed explanations and code cells for training the diffusion model and visualizing the image generation process.

### Running the Evaluator:

1. Ensure that you have the necessary dependencies installed. You can install them using the following command:
   ```bash
   pip install -r requirements.txt
   ```

2. Run the `evaluator.py` script, providing the paths to the reference batch and the sample batch as command-line arguments:
   ```bash
   python evaluator.py path/to/reference_batch path/to/sample_batch
   ```
   Here are links to download all of the sample and reference batches:

   * LSUN bedroom:
     * [reference batch](https://openaipublic.blob.core.windows.net/diffusion/jul-2021/ref_batches/lsun/bedroom/VIRTUAL_lsun_bedroom256.npz)
     * [DDPM](https://openaipublic.blob.core.windows.net/diffusion/jul-2021/ref_batches/lsun/bedroom/ddpm_lsun_bedroom.npz)

3. The script will compute and print evaluation metrics, including FID, precision, and recall, for comparing the generated images with the reference images.
* Here are the values obtained by running on above batches

  * | Metric       | Value                               |
    |--------------|-------------------------------------|
    | FID          | 4.886800342793833                   |
    | sFID         | 9.06836742894393                    |
    | Precision    |  0.60118                            |
    | Recall       | 0.4504                              |
## References
1. [Denoising Diffusion Probabilistic Models Paper](https://arxiv.org/abs/2006.11239)
2. [LSUN Bedroom Dataset Repository](https://github.com/fyu/lsun)
3. Evaluation metrics
   - [FID score](https://github.com/bioinf-jku/TTUR/blob/73ab375cdf952a12686d9aa7978567771084da42/fid.py#L109)
   - [Precission and Recall](https://github.com/openai/guided-diffusion/blob/22e0df8183507e13a7813f8d38d51b072ca1e67c/evaluations/evaluator.py#L194C7-L194C7) 
