#################################################################################################################
# Script name: Merge_PDF_Toolbox.py
# Author(s): Zand Bakhtiari
# Date : October 30, 2018
# Description: This script will take all PDF documents in a folder and merge 
# them into one PDF document in a specified output folder.
#################################################################################################################

# Import Modules
import arcpy, os, glob

# Folder where PDFs will be stored
pdfFolder = arcpy.GetParameterAsText(0)
# Folder where final merged PDF will be stored
pdfname = arcpy.GetParameterAsText(1)
# Name of the finale merged PDF
mergedpdf = arcpy.GetParameterAsText(2)
# Creates a file path for the final PDF document  
finalpdf = pdfname + os.sep + mergedpdf + '.pdf'

#%%
if os.path.exists(finalpdf):
    os.remove(finalpdf)
#%%

# Creates a list of the PDF file paths
pdflist = glob.glob(pdfFolder + os.sep + '*.pdf')

#%%

pdfDoc = arcpy.mapping.PDFDocumentCreate(finalpdf)
for p in pdflist:
    pdfDoc.appendPages(p)
pdfDoc.saveAndClose()
del pdfDoc




