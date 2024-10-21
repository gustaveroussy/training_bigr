#how to re-create the html file  
git clone https://github.com/gustaveroussy/training_bigr.git  
cd training_bigr/Make_graphs_under_R_with_ggplot2/For_Teachers  
cp ../For_Students/Clinical_Cohort_full.csv ./
wget https://zenodo.org/records/13963480/files/formation_bigr_make_graphs_under_R_with_ggplot2.simg
singularity exec --no-home -B ./:/home/ formation_bigr_make_graphs_under_R_with_ggplot2.simg R -e 'rmarkdown::render("/home/Make_graphs_under_R_with_ggplot2.Rmd")'  
mv Make_graphs_under_R_with_ggplot2.html ../For_Students/  
rm -r Clinical_Cohort_full.csv
rm formation_bigr_make_graphs_under_R_with_ggplot2.simg
