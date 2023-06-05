How does it work?
=====

QR Code scanning
------------

The first thing you'll come across when you open the app will be a QR Code scanner view.

The LogBookPics app works by scanning a simple QR Code via your camera. 

This QR Code contains a URL that has a JSON file containing various field, among which we find:

- ``title``: it contains the title of the LogBook
  
- ``info``: it contains the info of our LogBook
  
- ``inputimage``: it either contains a Base64 encoded image binary or a string ("camera" or "file" we'll discuss about this later in the page)
  
- ``guicomponents``: a series of components that the LogBook has (again, this topic will be discussed later in the page)
  

These are the most important components of the JSON we got from the URL

Image acquisition
------------

After the image has been acquired from QR Code's URL, we show an image preview.

In our program, we keep a reference of the imageBitmap. This reference can be accessed in all of the program's classes.

When the QR Code is scanned we:

- If ``inputimage`` is an encoded Base64, we decode it and save it into our imageBitmap reference;
  
- If ``inputimage`` is a string that is equal to ``camera``, we open a camera view that will take a photograph and save it in our imageBitmap reference;
  
- If ``inputimage`` is a string that is equal to ``file``, we open the phone's gallery and let the user select a photo to save in our imageBitmap reference.



Image annotation
------------
The image annotation tools are explained in the usage page (TODO insert link to page and section).

We then proceed to write the new imageBitmap to our ``postJSON``, which is a copy of the JSON we recieved

Component System
------------
The component system works by parsing the ``guicomponents`` part of the JSON we got into coherent components.
In the Component System view, you'll be able to add or remove components to your liking