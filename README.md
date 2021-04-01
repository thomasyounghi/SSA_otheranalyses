# SSA_otheranalyses

This repository contains additional analyses of single cell data from a study
to measure changes in the efficiency of a specific DNA repair pathway with age.
That study found that a specific DNA repair pathway called SSA declines in
 efficiency from 90% to about 70% when comparing young (< 5 generation old)
 and older (~18 generation old) cells. I subsequently showed that this decline
 in efficiency was linked to changes in cell cycle progression in older cells.

## What kind of data was collected in the previous study?

In the previous study, the fluorescence of individual old and young yeast cells were measured over time. During that time period a double strand break was induced a single cassette in the genome, and repair was measured using a fluorescent YFP reporter that was designed to be produced if SSA succesfully occurred . Production of YFP signal after its absence was used to assess whether SSA repair occurred.

The repair cassette also contained a RFP expression sequence directly adjacent to the cut site. Cutting of the cassette would be expected to halt production of RFP mRNA. Dilution of existing RFP by cell growth would result in a decline in RFP fluorescence. Permanent loss of the RFP gene by SSA, other repair pathways, or lack of repair combined with dilution would eventually cause fluorescence to decline to background levels. Therefore, drops in RFP fluorescence can be a potential reporter for cutting of the repair cassette and/or repair.

Cell division provides a third important piece of information about the cells in the study. Cells typically arrest their cell cycle in response to DNA double-strand breaks. A halt in cell division can provide potential evidence of DNA damage induced cell cycle arrest. Cell division also typically slows down as cells reach the end of their replicative lifespan, so a slow down can provide evidence that cell's are indeed old.  Finally cell division events provide important context for the YFP and RFP signal. Rapidly dividing cells would be expected to have a lower YFP and RFP signals, for the same rate of YFP and RFP protein production.  In this study, cell division was measured by the time of appearance of daughter buds in each cell.

Looking at measurements of YFP, RFP, and cell division in individual cells could provide valuable insight into the dynamics of repair.The timing of YFP production could indicate the speed of repair or expression following repair. The timing of RFP loss, accounting for cell division, could indicate the timing of cutting of the cassette. The previous study already showed that changes in cell division with age drive changes in SSA repair efficiency (fraction of cells that are able to repair). Due to their potential to provide insight into DNA repair for the cells in the experiment, it makes sense to pursue a a thorough investigation of the single cell measurement trajectories.


## Description of analyses

SingleCellTrajectories_clustering.Rmd  
This notebook applies Ward's method to cluster single cell RFP trajectories
for cells of different strain and age cohorts. It is intended to provide
a general sense of the types of patterns exhibited by single cell RFP trajectories in different strains

YFP_timetoevent.Rmd  
This notebook applies techniques from survival analysis (Kaplan Meier curves,
Cumulative Incidence For Competing Risks, and Cause Specific Hazards) to understand differences in time-to-YFP appearance between strains and age groups.  
 
