# Write audio data to tfrecords format for training Neural networks

TFrecordmananger is one of the record formatting manager used in DSGenerator to generate parameter files.

Within the context of DSGenerator, Tfrecords are specified in the custom configuration file as "Tfrecords" for the key value *"recordFormat"*. In the config file:

		"recordFormat": "tfrecords",

## Usage of TensorFlow

The key-value pairs for parameters specified in configuration file are stored as as Featurelists provided by tensorflow format.

The tensorflow feature for the DSSYnth class and audio file specifications are constructed using the keys in the configuration file.

		| Key | #TF Feature| 
		| :---: | :---: |
		| pfname | bytes_list | 
		| soundDuration  float_list |
		| segmentNum| int64_list | 


The tensorflow feature for sound labels are constructed by stringing the parameterName and parameter's attribute. 
The example describes features for the parameter value of *cf* (center frequency).

	
		| Key | #TF Feature| 
		| :---: | :---: |
		| cf | float_list| 
		| cf_synth_units|  float_list |
		| cf_user_nvals| int64_list | 
		| cf_user_minval|float_list |
		| cf_user_maxval | float_list|
		| cf_synth_minval| float_list| 
		| cf__synth_maxval| float_list| 

For fixed parameters in the configuration files, the minval and maxval for synth and user parameters are set to infinity.



