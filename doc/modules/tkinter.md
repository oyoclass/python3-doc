## tkinter


### Quick Examples

#### 1, Simple messsage box

```python
from tkinter import *
# create a window instance
window = Tk()
# set window title
window.title("Welcome")
# set window size: 350 x 200
window.geometry("350x200")
# create a text label
lbl = Label(window, text="Hello")
# show the label at top-left corner
lbl.grid(column=0, row=0)
# show this window
window.mainloop()
```

Copy the above code to Python3 editor in OYOclass, then click "Run", you will see the running result like fhe following:

<img src="/assets/img/tkinter-msgbox.png" width="400px"/>
