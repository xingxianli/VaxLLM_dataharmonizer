# VaxLLM_DataHarmonizer

DataHarmonizer is a standardized browser-based spreadsheet editor and validator that can be run offline and locally. DataHarmonizer project was created by the Centre for Infectious Disease Genomics and One Health (CIDGOH) at Simon Fraser University. VaxLLM working group developed a template fitting VaxLLM's model output to help experts validate the results of the large language model. 

## Simple Video Tutorial
https://github.com/user-attachments/assets/61937f22-dcfc-4333-ac66-543f39d7836c

## Features

1. Choose “brucella vaccine schema” template
2. Upload files : only accepts Excel (.xlsx) or CSV (.csv) files.
3. Validation feature: checks for missing required fields, invalid vaccine types and incorrect values.
4. Download output: Provides a cleaned and harmonized version of the uploaded 

## Web deploy (use directly)

website: https://vaxllm-web.onrender.com

This is static site constucted using render.com.

The repository used for static site : https://github.com/xingxianli/VaxLLM_web

## Run offline
Open `web/dist/index.html` in your browser.

## Developer guide

### Local setup

1. Clone the repository: 
```bash 
> git clone
```

2. locate the folder:
   
```bash
> cd data-harmonizer
```

3. Install dependencies:
```bash
> pip install -r requirements.txt
```
4. Run the program

```bash
> yarn dev
```

### How to edit the template?
Locate `web/template/VaxLLM`

Edit schema.yaml to change template

Run `python ../../../script/linkml.py -i schema.yaml` to save to json

More details located at https://github.com/cidgoh/DataHarmonizer/wiki/DataHarmonizer-Templates.

## Citation

**The DataHarmonizer: a tool for faster data harmonization, validation, aggregation and analysis of pathogen genomics contextual information**

Microbial Genomics (9:1) 2023

DOI: https://doi.org/10.1099/mgen.0.000908

_Ivan S. Gill, Emma J. Griffiths​, Damion Dooley​, Rhiannon Cameron​, Sarah Savić Kallesøe​, Nithu Sara John​, Anoosha Sehar​, Gurinder Gosal​, David Alexander​, Madison Chapel​, Matthew A. Croxen​​, Benjamin Delisle​, Rachelle Di Tullio​, Daniel Gaston​, Ana Duggan​, Jennifer L. Guthrie​, Mark Horsman4​, Esha Joshi​, Levon Kearny​, Natalie Knox​, Lynette Lau​, Jason J. LeBlanc9, Vincent Li​, Pierre Lyons​, Keith MacKenzie1, Andrew G. McArthur​, Emily M. Panousis​, John Palmer​, Natalie Prystajecky​, Kerri N. Smith​, Jennifer Tanner​, Christopher Townend​, Andrea Tyler, Gary Van Domselaar​, William W. L. Hsiao_
