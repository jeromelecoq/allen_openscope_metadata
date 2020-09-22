# Credit Assignment Project Metadata Code

This repository hosts the metadata for data for the Credit Assignment project, an [**Allen Institute for Brain Science**](https://alleninstitute.org/what-we-do/brain-science/) [**OpenScope**](https://alleninstitute.org/what-we-do/brain-science/news-press/press-releases/openscope-first-shared-observatory-neuroscience) project. 

The experiment details, analyses and results are published in [Gillon _et al._, 2021, _bioRxiv_](https://www.biorxiv.org/content/10.1101/2021.01.15.426915v1).

&nbsp;

## Metadata spreadsheet
`metadata.csv` contains the metadata for the Credit Assignment project data, organized in the following columns:

- `dandiset` : Dandi dataset number  

- `dandi_allen_subject_id` : Dandi/Allen subject unique ID (6 digits)  

- `dandi_session_id` : Dandi session ID (constructed from the session start date and time in **UTC**: YYYYMMDD**T**HHMMSS)

- `allen_session_id` : Allen session unique ID (9 digits)  

- `local_subject_n` : subject number used within the project  

- `local_session_n` : session number for the subject

- `imaging_date` : imaging date in **local** time (YYYYMMDD)

- `imaging_depth` : target imaging depth (in  &mu;m)  

- `imaging_cell_layer` : cortical layer to which the imaged cells belong (`L2/3` or `L5`)  

- `imaging_plane` : imaging plane (`somata` or `distal_apical_dendrites`)  

- `n_ROIs` : number of regions of interest (ROIs) identified  

- `allen_QC` : whether the session was deemed to have `passed` or `failed` quality control (QC)   

- `stimulus_seed` : random number generator seed used to generate the stimuli for the session  

- `experimental_notes` : additional notes, typically related to QC  

&nbsp;

## Additional information
- **Data:** The data for this project is hosted [here](https://gui.dandiarchive.org/#/dandiset/000037) in the DANDI archive in [NWB](https://www.nwb.org/) format.  

- **Recording region:** VisP, in the retinotopic center, unless indicated otherwise under `experimental_notes`.  

- **Recording modality:** GCamP6f (intracellular calcium) levels were measured using optical physiology.  

- **Somata:** Sessions labelled as recorded in the `somata` plane were recorded in the somata of L2/3 or L5 cells.  

- **Dendrites:** Sessions labelled as recorded in the `distal_apical_dendrites` plane were recorded in **cortical L1 in the distal apical dendrites** of L2/3 or L5 cells.  

- **Across sessions:** Recordings were made in the same plane across all sessions for each subject.  

- **ROIs**: In the somatic planes, ROIs were identified using the [Visual Coding pipeline](https://www.biorxiv.org/content/10.1101/359513v1). In the apical dendritic planes, ROIs were identified using [Inan *et al.*, 2021](https://www.biorxiv.org/content/10.1101/2021.03.24.436279v2)'s `robust estimation algorithm (EXTRACT)`. Both sets of ROIs were pre-processed using the Visual Coding pipeline. ROIs that overlapped with the motion border, or were duplicates, unions, empty, or noisy were removed.   

- **Quality control (QC)**: The Visual Coding QC pipeline automatically evaluated subject state, as well as stimulus visualization and recording quality (e.g., by checking for dropped frames) to determine whether a recording session was of sufficient quality to be included in the analysis dataset. Flagged sessions for review were then manually determined to have passed or failed.  

- **Stimuli**: For detailed information and source code, see the [Credit Assignment stimuli repository](https://github.com/colleenjg/cred_assign_stimuli).  
&nbsp;

## Notes
- Any apparent discrepancy in date between `dandi_session_id` and `imaging_date` is explained by the fact that:
    
    * `dandi_session_id` reflects session start date and time in the **UTC** time zone.

    * `imaging_date` reflects session start date in **local** time (PST/PDT, i.e., UTC - 8h/7h, depending on time of year).



