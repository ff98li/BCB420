[Compiled report](https://ff98li.github.io/BCB420/index.html)

## Before compiling the notebook...

1. In the directory where you pull the repository, execute the following command in os shell:
  - Windows: `docker run --rm -t -v ${PWD}\Feifei_Li:/home/rstudio/projects --add-host "localhost:<your_local_ip_address>" --user rstudio risserlin/em_base_image /usr/local/bin/R -e "rmarkdown::render('/home/rstudio/projects/A3_Feifei_Li.Rmd', output_file='/home/rstudio/projects/index.html')"`
  - MacOS/Linux: `docker run --rm -t -v "$(pwd)"/Feifei_Li:/home/rstudio/projects --add-host "localhost:<your_local_ip_address>" --user rstudio risserlin/em_base_image /usr/local/bin/R -e "rmarkdown::render('/home/rstudio/projects/A3_Feifei_Li.Rmd', output_file='/home/rstudio/projects/index.html')"`
  - Change `<your_ip_address>` to your local ip address (important step, or otherwise it cannot detect Cytoscape running)
2. Have Cytoscape open.
3. In the YAML metadata of `A3_Feifei_Li.Rmd`:
 - Change `isWindows` to `FALSE` if you are not compiling on a host machine running Windows OS.
 - If you perfer to use your own version of EnrichmentMap app, please change `hasEM` to `TRUE`, or otherwise it will automatically update your EnrichmentMap app to the current Cytoscape release (3.3.1)
 - Change `isBeta` according to your version of EnrichmentMap app:
   - `TRUE` for 3.3.2 or higher, `FALSE` for version below 3.3.2
 - Change `host_machine_dir` to the directory where you pull this repository. e.g.
   - Windows OS: `C:\\<path_to_repo>\\Feifei_Li`
   - MacOS/Linux: `/Users/<your username>/Feifei_Li`

Now the notebook is ready to be compiled.

Generated plots will be stored under `./screenshots/` directory, and data files generated when compiling the notebook will be saved in `./data/`.
You might delete these directories once the compilation is complete.
