# UNet-based-Seismic-Processing (CS300)
UNet-based Framework for Multiple Seismic Processing Tasks.

In order to run the code:

- clone the following repository: https://github.com/swag-kaust/storseismic/tree/main

- enter the directory of that repository, and upload the notobooks present here (DATASET_PREPARATION, TEST_VIKING_GRABEN_DATASET etc.)

- create a conda environment with the package in requirements.txt or environment.yml packages. Make sure to install pytorch and obspy.

- run first the DATASET_PREPARATION script, uploading the seismic sections (torch.load(r"/data_raw/raw_marmousi.pt",weights_only=True)) in the folder you placed them. You need to have the Marmousi dataset I used, that was given to me by a geophysicist. I can send you the data, the only issue is that they are several gigabytes.

- run the other scripts except for TEST_VIKING_GRABEN_DATASET, paying attention to correctly loading the data saved in the previous script and also correctly loading the checkpoints present in this directory. I cannot load the UNet++ checkpoint since they occupy to much memory, but you can train it from scratch, commenting these lines of code when loading the model:
#checkpoint_path = "best_unetPP2_model_superresolution_denoising_interpolation.pth"
#model.load_state_dict(torch.load(checkpoint_path, map_location=device))

- run TEST_VIKING_GRABEN_DATASET, loading the Viking Graben dataset (I can provide the data if you are encountering some issues)

Contact me for any issue if you fail in reproducing the code.
