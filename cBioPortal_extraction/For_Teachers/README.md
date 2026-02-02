#how to re-create the html file  
git clone https://github.com/gustaveroussy/training_bigr.git  
cd training_bigr/cBioPortal_extraction/For_Teachers  
wget https://zenodo.org/records/18455694/files/formation_bigr_cBioPortal_extraction.simg
singularity exec --no-home -B ${HOME}/.Renviron -B ./:/home/render/ formation_bigr_cBioPortal_extraction.simg R -e 'rmarkdown::render("/home/render/cBioPortal_extraction.Rmd")'  
mv cBioPortal_extraction.html ../For_Students/  
rm formation_bigr_cBioPortal_extraction.simg
