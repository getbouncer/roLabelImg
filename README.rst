roLabelImg (fork)
========

This version is a fork of the original roLabelImg project here: <https://github.com/tzutalin/labelImg>.

This version's purpose is solely to simplify the process of labeling cards.

It is written in Python and uses Qt for its graphical interface.

Installation
------------------

Build from source
~~~~~~~~~~~~~~~~~

Linux/Ubuntu/Mac requires at least `Python
2.6 <http://www.python.org/getit/>`__ and has been tested with `PyQt
4.8 <http://www.riverbankcomputing.co.uk/software/pyqt/intro>`__.


Ubuntu Linux
^^^^^^^^^^^^
Python 3 + Qt5

.. code::

    sudo apt-get install pyqt5-dev-tools
    sudo pip3 install -r requirements/requirements-linux-python3.txt
    make qt5py3
    python3 labelImg.py

OS X
^^^^
Python 3 + Qt5

.. code::

    brew install python3 # if needed. Try `which python3` first
    brew install qt
    pip3 install pipenv
    pipenv --three # or pipenv install pyqt5 lxml
    pipenv run pip install pyqt5 lxml
    pipenv run make qt5py3
    python3 labelImg.py

Windows
^^^^^^^

Download and setup `Python 2.6 or
later <https://www.python.org/downloads/windows/>`__,
`PyQt4 <https://www.riverbankcomputing.com/software/pyqt/download>`__
and `install lxml <http://lxml.de/installation.html>`__.

Open cmd and go to `labelImg <#labelimg>`__ directory

.. code::

    pyrcc4 -o resources.py resources.qrc
    python labelImg.py
    python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

Usage
-----

Steps
~~~~~

1. Build and launch using the instructions above.
2. Click 'Open Dir'
3. Click 'Create RectBox'
4. Click and release left mouse to select a region to annotate the rect
   box
5. You can use right mouse to drag the rect box to copy or move it

The annotation will be saved to the folder you specify.

You can refer to the below hotkeys to speed up your workflow.

Hotkeys
~~~~~~~

+------------+--------------------------------------------+
| Ctrl + u   | Load all of the images from a directory    |
+------------+--------------------------------------------+
| Ctrl + r   | Change the default annotation target dir   |
+------------+--------------------------------------------+
| Ctrl + s   | Save                                       |
+------------+--------------------------------------------+
| Ctrl + d   | Copy the current label and rect box        |
+------------+--------------------------------------------+
| Space      | Flag the current image as verified         |
+------------+--------------------------------------------+
| w          | Create a rect box                          |
+------------+--------------------------------------------+
| e          | Create a Rotated rect box                  |
+------------+--------------------------------------------+
| d          | Next image                                 |
+------------+--------------------------------------------+
| a          | Previous image                             |
+------------+--------------------------------------------+
| r          | Hidden/Show Rotated Rect boxes             |
+------------+--------------------------------------------+
| n          | Hidden/Show Normal Rect boxes              |
+------------+--------------------------------------------+
| del        | Delete the selected rect box               |
+------------+--------------------------------------------+
| Ctrl++     | Zoom in                                    |
+------------+--------------------------------------------+
| Ctrl--     | Zoom out                                   |
+------------+--------------------------------------------+
| ↑→↓←       | Keyboard arrows to move selected rect box  |
+------------+--------------------------------------------+
| zxcv       | Keyboard to rotate selected rect box       |
+------------+--------------------------------------------+

`Watch a demo by author cgvict`

.. image:: https://raw.githubusercontent.com/cgvict/roLabelImg/master/demo/demo4.png
     :alt: Demo Image

.. image:: https://raw.githubusercontent.com/cgvict/roLabelImg/master/demo/roLabelImg.gif

Annotations are saved as XML files almost like PASCAL VOC format, the format used by `ImageNet <http://www.image-net.org/>`__.


XML Format
------------------

.. code::

    <annotation verified="yes">
      <folder>hsrc</folder>
      <filename>100000001</filename>
      <path>/Users/haoyou/Library/Mobile Documents/com~apple~CloudDocs/OneDrive/hsrc/100000001.bmp</path>
      <source>
        <database>Unknown</database>
      </source>
      <size>
        <width>1166</width>
        <height>753</height>
        <depth>3</depth>
      </size>
      <segmented>0</segmented>
      <object>
        <type>bndbox</type>
        <name>ship</name>
        <pose>Unspecified</pose>
        <truncated>0</truncated>
        <difficult>0</difficult>
        <bndbox>
          <xmin>178</xmin>
          <ymin>246</ymin>
          <xmax>974</xmax>
          <ymax>504</ymax>
        </bndbox>
      </object>
      <object>
        <type>robndbox</type>
        <name>ship</name>
        <pose>Unspecified</pose>
        <truncated>0</truncated>
        <difficult>0</difficult>
        <robndbox>
          <cx>580.7887</cx>
          <cy>343.2913</cy>
          <w>775.0449</w>
          <h>170.2159</h>
          <angle>2.889813</angle>
        </robndbox>
      </object>
    </annotation>


How to contribute
~~~~~~~~~~~~~~~~~

Send a pull request

License
~~~~~~~
`Free software: MIT license <https://github.com/cgvict/roLabelImg/blob/master/LICENSE>`_
