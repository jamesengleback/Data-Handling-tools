# Data-Handling-tools

Some of my tools for data as comes off the machines
# [UV-Vis Spectrometer data analysis and plotting](https://github.com/jamesengleback/Data-Handling-tools/blob/master/20180623%20-%20Varian%20Spec%20data.ipynb)
This was a notebook I used to process [UV-Vis](https://en.wikipedia.org/wiki/Ultraviolet%E2%80%93visible_spectroscopy) data from [titration](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4756639/) experiments on [P450 Enzymes](https://en.wikipedia.org/wiki/Cytochrome_P450), which is what [my lab](https://www.research.manchester.ac.uk/portal/andrew.munro.html) work on. 
The .csv files that are generated by our spectrometers need some wrangling, which I did using [pandas](https://pandas.pydata.org/), then there are a few [pyplot](https://matplotlib.org/api/pyplot_api.html) plots:
The absorbance between 200 and 800 nm for my [P450](https://www.ncbi.nlm.nih.gov/pubmed/12076537) as it sits in a [cuvette](https://en.wikipedia.org/wiki/Cuvette) and I add increments of a [compound it binds with](https://pubchem.ncbi.nlm.nih.gov/compound/Fluazifop). (Sorry for not doing a colormap! It's on my list)
![Raw spec](20190427_Raw_UVVis_Spectra.png)

To get a better look at how the [absorption profile](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3041835/) changes as compound is added, we subtract the first (compound-free) profile from all of the other traces. Check it out:
![Difference Spectra](20190427UVVis_Difference_Spectra.png)

The Differences in absorbance at around 280 nm I think are a result of is known as [funny business](https://en.wikipedia.org/wiki/Absorption_spectroscopy), so I'm ignoring them for now. We're interested in the changes at around 390 and 420 nm, which is where the enzyme's [heme](https://en.wikipedia.org/wiki/Heme) attachment shifts its absorbance profile in [response to binding to a compound](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3041835/).

If we plot how much the absorbance changes at 390 and 420 nm in response to adding my compound we get this:
![MichaelisMenten](20190427UVVis_Michaelis_Menten_plot.png)
This [Michaelis-Menten saturation curve ](https://en.wikipedia.org/wiki/Michaelis%E2%80%93Menten_kinetics) was fit to the data points by parameterising the e
