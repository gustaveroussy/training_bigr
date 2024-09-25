#how to re-create the html file  
git clone https://github.com/gustaveroussy/training_bigr.git  
cd training_bigr/Tables_manipulation/For_Teachers  
cp ../For_Students/Clinical* ./  
cp ../For_Students/Sample* ./  
singularity exec --no-home -B ./:/home/ formation_bigr_tables_manipulation.simg R -e 'rmarkdown::render("/home/Tables_manipulation.Rmd")'  
mv Tables_manipulation.html ../For_Students/  
rm -r Clinical*  
rm -r Sample*  
