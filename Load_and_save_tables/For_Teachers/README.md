#how to re-create the html file
git clone https://github.com/gustaveroussy/training_bigr.git
cd training_bigr/Load_and_save_tables/For_Teachers
cp ../For_Students/*counts* ./
wget https://zenodo.org/records/13961326/files/formation_bigr_load_and_save_table.simg
singularity exec --no-home -B ./:/home/ formation_bigr_load_and_save_table.simg R -e 'rmarkdown::render("/home/Load_and_save_tables_in_R.Rmd")'  
mv Load_and_save_tables_in_R.html ../For_Students/
rm -r *counts*
rm formation_bigr_load_and_save_table.simg
