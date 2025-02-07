# scCODI
Global and cross-omics feature aggregation improves single-cell multi-omics integration and clustering.

scCODI, an innovative cross-omics deep learning model for integrating single-cell multi-omics data for cell clustering. This model processes paired omics datasets, specifically single-cell transcriptomics in conjunction with either epigenomics or proteomics data to enable a comprehensive exploration of cellular heterogeneity. Specifically, the shared representation of two omics is obtained through cross-omics feature aggregation, thereby fully leveraging the complementarity of different omics within the same cell. Moreover, we align the omic-specific representation and shared representation of the same cell through the global relationship-guided contrastive learning module, making the representations of the same cell in both the shared and omic-specific omics more similar.

![Sample Image]([https://github.com/Chengchenyang53/scCODI/blob/master/model.png])

# Dependencies
Python 3.8.1

Pytorch 1.6.0

Scanpy 1.6.0

SKlearn 0.22.1

Numpy 1.18.1

h5py 2.9.0

### Setting Up the Environment
1) **Create a virtual environment:**

`conda create -n scCODI python=3.8` 

` conda activate scCODI` 

2) **Install dependencies:**

`pip install -r requirements.txt` 

3) **Update transformer:**

Before run, please carefully read  'S_update_transformer.docs', and refer to the steps inside it to modify the code in order to get S.

# Run scCODI
1) Prepare the input data in h5 format.
   
2) RNA and ATAC : 

`python -u main.py --n_clusters 'num_cluster' --ae_weight_file 'AE_weight_file' --data_file datafile
--save_dir ../result --embedding_file --prediction_file --filter1 --filter2 --f1 2000 --f2 2000 -el 256 128 64 -dl1 64 128 256 -dl2 64 128 256` 

3) RNA and ADT : 

`python -u main.py --n_clusters 'num_cluster' --ae_weight_file 'AE_weight_file' --data_file datafile
--save_dir ../result --embedding_file --prediction_file`

# Output of scCODI
scCODI outputs a latent representation of data which can be used for further downstream analyses and visualized by t-SNE or Umap.

