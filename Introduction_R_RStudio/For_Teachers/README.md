#how to re-create the html file  
git clone https://github.com/gustaveroussy/training_bigr.git  
cd training_bigr/Introduction_R_RStudio/For_Teachers  
cp ../For_Students/example_table.csv ./  
wget https://zenodo.org/records/13961326/files/formation_bigr_introduction_R_RStudio.simg
singularity exec --no-home -B ./:/home/ formation_bigr_introduction_R_RStudio.simg R -e 'rmarkdown::render("/home/GR_IntroR_RStudio.Rmd")'  
mv GR_IntroR_RStudio.html ../For_Students/  
rm -r example_table.csv
rm formation_bigr_introduction_R_RStudio.simg
