# S20-team2-project

This is the README document for Shawn Mace's branch of Team2 (Pandomonium). The assumption is the first part of applied convolution net to attempt to solve the colliding galaxies issue is dependent of the fucntionality of the main CNN designed by other group members. My task is visualize the weights and activations of the group CNN. Below describes the steps taken, or needing to be taken, to fullfil the assignment.

## Weights
As per Lab 6

## Activations
My initial design uses Keras to display activations of the project CNN through ModelCheckpoints and Callbacks.

“In order to extract the feature maps we want to look at, we’ll create a Keras model that takes batches of images as input, and outputs the activations of all convolution and pooling layers. To do this, we’ll use the Keras class Model. A model is instantiated using two arguments: an input tensor (or list of input tensors) and an output tensor (or list of output tensors). The resulting class is a Keras model, just like the Sequential models, mapping the specified inputs to the specified outputs. What sets the Model class apart is that it allows for models with multiple outputs, unlike Sequential.” - Francois Challet, "DEEP LEARNING with Python"

Using Karas with Callbacks and Checkpoints - https://keras.io/callbacks/
As an example, below we use the Keras function to capture the best-fitting weight into a file called "highest_weight". For simplicity the suffix is generalized, though I am researching HDMF5 format (a hierarchial data format which supports large, complex, heterogeneous data) to store any needed weights, activations, or other data needing to be represented. The code creates a checkpoint that tests the weights on each epoch and stores the highest (i.e. most useful) to a file.
Slightly more generalized collection methods:
-- model.save_weights(filepath) saves the weights of the model as a HDF5 file.
-- model.load_weights(filepath, by_name=False) loads the weights of the model from a HDF5 file (created by save_weights). By default, the architecture is expected to be unchanged. To load weights into a different architecture (with some layers in common), use by_name=True to load only those layers with the same name. - https://keras.io/models/model/

The saved weight will be added to new iterations of the CNN to provide a practical starting point for testing the next batch. When .fit is ran it should contain a new field to callback to the checkpoint.

**callbacks=[GetWeights],**

The process is easy from here. The CNN is retrained with the best weights and we can use this training to predict outcomes with images outside of our training or validation set. Below is a code snippet from https://towardsdatascience.com/visualizing-intermediate-activation-in-convolutional-neural-networks-with-keras-260b36d60d0
It shows the process that follows this which is predicting and plotting the resulting activation values. We can also access the updated weights.

layer_names = [] <br>
layer in classifier.layers[:12]: layer_names.append(layer.name) 

Images_per_row = 16

for layer_name, layer_activation in zip(layer_names, activations): # Displays the feature maps <br>
  n_features = layer_activation.shape[-1] # Number of features in the feature map <br>
  size = layer_activation.shape[1] #The feature map has shape (1, size, size, n_features). <br>
   n_cols = n_features // images_per_row # Tiles the activation channels in this matrix <br>
   display_grid = np.zeros((size * n_cols, images_per_row * size)) <br>
   for col in range(n_cols): # Tiles each filter into a big horizontal grid <br>
      for row in range(images_per_row): <br>
          channel_image = layer_activation[0, :, :, col * images_per_row + row] <br>
          channel_image -= channel_image.mean() # Post-processes the feature to make it visually palatable <br>
          channel_image /= channel_image.std() <br>
          channel_image *= 64 <br>
          channel_image += 128 <br>
          channel_image = np.clip(channel_image, 0, 255).astype('uint8') <br>
          display_grid[col * size : (col + 1) * size, # Displays the grid <br>
              row * size : (row + 1) * size] = channel_image <br>
          scale = 1. / size <br>
          <br>
   plt.figure(figsize=(scale * display_grid.shape[1], scale * display_grid.shape[0])) <br>
   plt.title(layer_name) <br>
   plt.grid(False) <br>
   plt.imshow(display_grid, aspect='auto', cmap='viridis')<br>

## Other Visual Representations
This is where I will expand on obtaining other representation where applicable.

To be added
