# Change-Detection-in-Dynamic-Event-Attributes

The jupyter notebook "Event_Log_Generation.ipynb" in this repository creates the event log for the evaluation in the paper "Change Detection in Dynamic Event Attributes". It uses the MIMIC-IV (https://physionet.org/content/mimiciv/1.0/) database, stored in a Postgres database. 
First, all cases related to acute kidney failure are retrieved. Then, the hospital data for their respective hospital admission is fetched, including laboratory values and demographic data. 
The database can be accessed via physionet, which requires CITI training for access (https://mimic.mit.edu/iv/).
The change detection is implemented as a python script in "Change_Detection.ipynb", which starts with the classification of event attributes according to their type (continuous vs. categorical) and their process characteristic (static, semi-dynamic, and dynamic), where this contribution focusses on dynamic event attributes. Then, it performs the statistical tests to generate the respective change analysis cells in the change detection cube.
The visualization of the change detection cube is implemented in the "UI.ipynb" notebook, allowing to perform the OLAP operations (Slice, Dice, Pivot, and Drill up/down). The UI can show views of slices of the cube by illustrating an event attribute change matrix, including the results of the change detection analysis for each change analyses cell. 

Therefore, consider the following steps to make it work:

1. Generate the event log by executing the jupyter notebook "Event_Log_Generation.ipynb".
2. Execute the jupyter notebook "Change_Detection.ipynb" taking the generated event log as its input.
3. Use the modified pm4py package provided by this repository. 
4. Execute the jupyter notebook "UI.ipynb" taking the generated change detection files as input. The last cell in the notebook shows the UI.


