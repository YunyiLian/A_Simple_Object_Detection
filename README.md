# A_Simple_Object_Detection
A school project of building an object detection model to detect candy objects in photos.

## Project Description
1. Created image dataset with labels using `Label Studio` to manually label 8 different candies. Labels include `Moon`, `Insect`, `Black_satr`, `Grey_star`, `Unicorn_whole`, `Unicorn_head`, `Owl` and `Cat`.
2. Imported the `.json` file containing the label information and used it to create Hugginface formatted annotations by building a function `formatted_ann`.
3. Built a function `transform_aug_ann` to combine the images and annotation transformations to use on a batch of examples.
4. Built a function `collate_fn` to batch all images together and pad images (currently are pixels) to the largest image in a batch, and create a corresponding `pixel_mask` to indicate which pixels are real (1) and which are padding (0).
5. Imported `AutoImageProcessor` pre-trained model from `transformers` library. Fine-tuned the model on the new training data.
6. Created a function `candy_counter` to load the fine-tuned model and take a picture of candies and return a dictionary with the counts of the different types of candies.
