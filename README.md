# Iterative-Neural-Style-Transfer
Tensorflow implementation of neural style transfer as proposed by Gatys et al.in the paper <a href="http://arxiv.org/abs/1508.06576">A Neural Algorithm of Artistic Style</a>

Sharing a simplified implementation of the style transfer algorithm. Code has been written and executed on GoogleCollab.

The below examples have been generated with 1000 iterations of Adam Optimizer (lr= 5.0 to 20.0) with content (_&alpha;_) and style (_&beta;_) weights set to roughly 1e1 and 1e-1 respectively.
The original paper mentioned that the ratio _&alpha;_/_&beta;_ was set to 1e-3, 1e-4 or 1e-5 but somehow I was not able to achieve good results with it.

Size of images ranged from 320x320 to 512x512 and took roughly 45-60 mins to train.

Different hyperparameter settings can be appropriate for different sets of images.

## Examples

### Content Images

<p align="center">
<img src="images/content/building.jpg" width="280" height="280"/>
<img src="images/content/dog.jpg" width="280" height="280"/>
<img src="images/content/knight.jpg" width="280" height="280"/>
</p>

### Style Images

<p align="center">
<img src="images/style/cubist.jpg" width="280" height="280"/>
<img src="images/style/starry_night.jpg" width="280" height="280"/>
<img src="images/style/patterned_leaves.jpg" width="280" height="280"/>
</p>

### Generated Images

<p align="center">
<img src="images/cubist_style_transfers/building-cubist_1000.jpg" width="280" height="280"/>
<img src="images/starry_night_style_transfers/building-starry_night_1000.jpg" width="280" height="280"/>
<img src="images/patterned_leaves_style_transfers/building-patterned_leaves_1000.jpg" width="280" height="280"/>
</p>


<p align="center">
<img src="images/cubist_style_transfers/dog-cubist_1000.jpg" width="280" height="280"/>
<img src="images/starry_night_style_transfers/dog-starry_night_1000.jpg" width="280" height="280"/>
<img src="images/patterned_leaves_style_transfers/dog-patterned_leaves_500.jpg" width="280" height="280"/>
</p>

<p align="center">
<img src="images/cubist_style_transfers/knight-cubist_1250.png" width="280" height="280"/>
<img src="images/starry_night_style_transfers/knight-starry_night_1000.jpg" width="280" height="280"/>
<img src="images/patterned_leaves_style_transfers/knight-patterned_leaves_1750.jpg" width="280" height="280"/>
</p>

### Usage
```
IMAGE_SIZE = <IMAGE_SIZE>
content_image_filename = <content_image_filename>
style_image_filename = <style_image_filename>
run_style_transfer(content_image_filename=content_image_filename,
                  style_image_filename=style_image_filename,
                  epochs=<number_of_epochs>,
                  learning_rate=<learning_rate>,
                  alpha=<content_weight>,
                  beta=<style_weight>
                  prefix=<prefix_of_generated_output_filenames>)
```

Example:
```
IMAGE_SIZE = 320
content_image_filename = './dog.jpg'
style_image_filename = './/starry_night.jpg'
run_style_transfer(content_image_filename=content_image_filename,
                  style_image_filename=style_image_filename,
                  epochs=1000,
                  learning_rate=10.0,
                  alpha=10,
                  beta=1e-1,
                  prefix='dog-starry_night')
``` 
