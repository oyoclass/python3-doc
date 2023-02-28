### Pillow

Pillow is an image processing library for Python.

### Examples

* All examples assume you have an image named `oyobot.png` inside a folder 
named `images` in your project. You may change the filename in the examples and
use your own image, or
<a download="oyobot.png" href="../../assets/img/oyobot.png" title="Download image">
    click here
</a> 
to download a copy.

#### Get Image Info

```python
from PIL import Image
img = Image.open('images/oyobot.png')

# print out image info
print(f'filename: {img.filename}')
print(f'dimensions: {img.width}x{img.height}')
print(f'format: {img.format}')
```

#### Render Image

```python
from PIL import Image
img = Image.open('images/oyobot.png')
img.show()
```

You will get an ImageMagick window rendered to the right of your code similar
to this:

<img src="../../assets/img/pillow-render.png" width="400px"/>


#### Apply a Filter to an Image

```python
from PIL import Image, ImageFilter
img = Image.open('images/oyobot.png')
img = img.filter(ImageFilter.GaussianBlur(20))
img.show()
```

You will get an ImageMagick window rendered to the right of your code similar 
to this:

<img src="../../assets/img/pillow-gaussian-blur.png" width="400px"/>


Read more at <a href="https://pillow.readthedocs.io/en/stable/">pillow.readthedocs.io</a>