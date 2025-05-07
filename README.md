GUI for fNIRS data viewing and lsl trigger editing.

A Python-based interactive viewer for functional Near-Infrared Spectroscopy (fNIRS) data with trigger management capabilities.

Overview:

fNIRS Viewer is an interactive tool designed for neuroscientists and researchers working with functional Near-Infrared Spectroscopy data. It provides a streamlined interface for visualizing fNIRS signals alongside event triggers, with robust capabilities for adding, editing, and managing experimental markers.

Features:

Data Visualization: Plot multiple fNIRS channels with customizable visibility
Trigger Management: Add, edit, delete, and clear experimental triggers
File Format Support:

fNIRS data: CSV, NPY, SNIRF (with MNE), NIRX (with MNE)
Trigger data: TSV (BIDS-compatible) and TRI files


Interactive Navigation:

Zoom in/out with persistent view state
Jump to start/end of recording
Show all data at once
Box zoom mode for detailed analysis


Synchronized Views: 

Channel and trigger displays remain synchronized during navigation
Channel Selection: Toggle visibility of individual channels for clearer visualization
Trigger Editing: Modify trigger positions and values with visual feedback
Data Export: Save modified triggers back to TSV or TRI files

Requirements:

Python 3.6+
NumPy
pandas
Matplotlib
ipywidgets
IPython
Optional: MNE (for SNIRF and NIRX file support)

# Install required dependencies
pip install numpy pandas matplotlib ipywidgets

# Optional: Install MNE for additional file format support
pip install mne

Usage
!Running in Jupyter Notebook!
python%matplotlib widget
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import ipywidgets as widgets
from IPython.display import display, clear_output
import os
import json
import warnings
from datetime import datetime, timedelta
warnings.filterwarnings('ignore')

Enter the path to your fNIRS data file in the "fNIRS Data" input field
Optionally, enter paths to trigger files (TSV and/or TRI formats)
Click "Load Data"

Viewing and Navigating

Use the navigation buttons to zoom in/out or jump to specific parts of the recording
Toggle the "Box Zoom" button to enable detailed region selection
Use the channel checkboxes to show/hide specific channels

Managing Triggers

Select a trigger value from the dropdown or enter a new one
Click "Add Trigger" to add a trigger at the center of the current view
Click on an existing trigger in the lower panel to select it
Use "Update Trigger" to change its value or "Delete Trigger" to remove it
Click "Clear Triggers" to remove all triggers

Saving Changes

Click "Save TSV" or "Save TRI" to save your modifications back to the original files

File Formats
Supported fNIRS Data Formats

CSV: First column as time, remaining columns as channel data
NPY: NumPy array with time in first column, or dictionary with 'time' and 'data' keys
SNIRF/NIRX: Requires MNE package for import

Supported Trigger Formats

TSV: Tab-separated values file with either:

BIDS format: Columns 'Onset', 'Duration', 'trial_type'
Simple format: Columns 'time', 'value'


TRI: Text file with format timestamp;sample_number;value

Troubleshooting

If the plot area remains blank, check that your file paths are correct
For large datasets, limit the number of visible channels to improve performance
If trigger timestamps don't align with fNIRS data, ensure both use the same time reference

Free for use with proper crediting, remember to cite: Åberg Lindell, R. (2025). GUI for fNIRS data viewing and lsl trigger editing. (Version 1). Zenodo. https://doi.org/10.5281/zenodo.15358609
Licensing: Creative Commons Attribution 4.0 International
