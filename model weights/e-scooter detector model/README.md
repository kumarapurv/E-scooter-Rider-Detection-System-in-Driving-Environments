
This folder contains the `h5` and `json` file of the trained model (used for inference)

Use the following code to load the model:

	# load json and create model
	json_file = open(".../e-scooter detector model/escooter_detector_model.json", 'r') #PATH OF THE FILE
	loaded_model_json = json_file.read()
	json_file.close()
	model = model_from_json(loaded_model_json)

	# load weights into new model
	model.load_weights(".../e-scooter detector model/escooter_detector_model.h5") #PATH OF THE FILE
	print("Loaded model from disk")

The model will be loaded to use in a variable called `model`.
