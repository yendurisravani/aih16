


1. ################# Activating the environment #############################
    Execute the following commands for activating the environment

	source SoftwarePacakage3.6/env/bin/activate  


2.  ##################Deeplab v3 ##############################
	a.  cd DeepLabV3_Plus-Tensorflow2.0-master/ 
	
	b.   Training Deeplab v3 (jupyter notebook)
		
		Execute the file train.ipynb
	
	c.   Inferencing/testing the trained Deeplab 

		Execute camvid_inference1.ipynb	

	d.   The outputs are saved in the outputs/ folder


This deeplabv3 needs tensorflow-2.0.0-rc0 and runs on CPU

3.  ##################ESP Net################################

	a.  cd dgx/ESPNet/

	b.   Training the ESP Net  (encoder) on the given local dataset
	
		python3 main.py --data_dir /home/aih16/datasetbackup/dataset/hsr --scaleIn 8 --batch_size 6 --savedir ./hsr --logFile hsrTrainEncoder.txt --cached_data_file hsr.p --classes 2

	c.   Training the ESP Net (decoder) on the given local dataset

		python3 main.py --data_dir /home/aih16/datasetbackup/dataset/hsr --scaleIn 1 –decoder True --batch_size 6 --savedir ./hsr --cached_data_file hsr_Decoder.p –pretrained ./hsr_enc_2_8/model_10.pth

	d.  This creates the hsr_enc_2_8/  hsr_dec_2_8/ directory which consists of the model weights for every epoch
	
	e. Visualization
		run /home/aih16/AIH19T-0210-Solution/AIHACK/ESPNet Visualization.ipynb

#########################Mask RCNN####################################

1.   cd   /home/aih16/AIH19T-0210-Solution/AIHACK/Mask_RCNN/samples
	run alert.ipynb
    This gives the segmentation masks and saved as the .png file and the predictions are saved to csv file
2.  For text generation part
    run text_generation.ipynb
  This gives the txt file which stores the calculated distances, angle, and directions from the segmented masks file
3.  For test to audio part
      run txt_to_audio.ipynb 
This gives the audio file for the previous text generated part.

##################################################################################



