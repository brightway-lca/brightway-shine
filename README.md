# brightway-shine

⚠️ this markdown file has been moved to the new Brightway documentation \
⚠️ this increases the visibility of the projects featured here \
⚠️ if you would like to add your project, please open a pull request on the page at the new documentation: \
https://documentation.brightway.dev/en/latest/source/other/ecosystem.html


This file links to other repositories outside the brightway-lca organization where the brightway code is extended or used.  

If you have a project that does this, please go ahead and add it here.

## Repositories that *extend* brightway
These repositories add some functionality to the core brightway-lca code base. 

### Activity Browser
A graphical user interface for brightway (cross platform and open source). It extends brightway in a number of way and provides users a more convenient way for standard tasks in brightway, such as inventory modeling and the analysis of LCA results.

https://github.com/LCA-ActivityBrowser/activity-browser

### presamples
Package to write, load, manage and verify numerical arrays, called presamples.  

Presamples can replace values in the matrices used in LCA as calculations are carried out. This integration is seamless in brightway2: 

```python
lca = bw.LCA({act:1}, presamples=[list_of_paths_to_presample_packages])
```

Storing and injecting specific values in LCA matrices can improve LCA calculations in many ways:

  * Storing and reusing data characterizing given scenarios makes scenario analysis much easier.
  * It can easily integrate time series.
  * It can use pre-generated static or stochastic values that were generated by complex, non-linear models, allowing the
    LCA model to capture system dynamics more accurately.
  * It is possible to account to correlation across parameters during Monte Carlo Simulations (e.g. for correlation
    between characterization factors, between fuel use and CO2 emissions, etc.
  * Since sampled data can be used directly, it is unnecessary to fit data to a distribution.

Presamples can also store parameters used in parameterized brightway models. 
https://presamples.readthedocs.io/en/latest/
https://github.com/PascalLesage/presamples

### brightway2-aggregated
This package provides tools for the creation and use of aggregated (i.e. cradle-to-gate) LCA data, both at the LCI and LCIA score level. 

https://github.com/CIRAIG/brightway2-aggregated
https://brightway2-aggregated.readthedocs.io/en/latest/

### bw2landbalancer
bw2landbalancer is a Python library used to create balanced land transformation samples to override unbalanced sample.

Unbalanced samples arise when land transformation exchanges are independently sampled. bw2landbalancer rescales certain land transformation exchanges to ensure that the ratio of land transformation from exchanges and land transformation to exchanges is conserved. It is based on the Brightway2 LCA framework, and is meant to be used with [presamples](https://github.com/PascalLesage/presamples).

https://github.com/CIRAIG/bw2landbalancer
[Notebook example on using bw2landbalancer](https://github.com/CIRAIG/bw2landbalancer/blob/master/Using%20bw2landbalancer.ipynb)

### bw2waterbalancer
bw2waterbalancer is a Python library used to create balanced water samples to override unbalanced sample.

Unbalanced samples arise when water exchanges are independently sampled. bw2waterbalancer rescales certain exchanges to ensure that the ratio of water inputs to water outputs is conserved. It is based on the Brightway2 LCA framework, and is meant to be used with [presamples](https://github.com/PascalLesage/presamples)..

https://github.com/CIRAIG/bw2waterbalancer

### lca_algebraic

This library is a layer above *Brightway2*, briging symbolic calculus to it, for the definition of parametric inventories with fast computation of impacts, suitable for global sensivity analyis, based on Monte Carlo method.

**[lca-algebraic](https://github.com/oie-mines-paristech/lca_algebraic)** provides a set of helper functions for :

* Compact & human readable definition of activites :
    * search background (tech and biosphere) activities
    * create new foreground activites with parametrized amounts
    * parametrize / update existing background activities (extending the class **Activity**)
* Definition of parameters
* Fast computation of LCAs
* Computation of Monte Carlo method and Global Sensivity Analysis (Sobol indices)


https://github.com/oie-mines-paristech/lca_algebraic



## Repositories that extensively *use* brightway2

### Global Sensitivity Analysis (Delta Moment-Independent Approach)
This repository implements the delta moment-independent GSA approach from SaLib and adds some smart filtering to reduce the number of GSA input variables. Still, this way the entire background can be included in GSA. It is based on previous Monte Carlo Analysis (methods for that included in the repository as it needs to store the LCA input and output data). An implementation is also available in the Activity Browser (https://github.com/LCA-ActivityBrowser/activity-browser).

https://github.com/bsteubing/lca-global-sensitivity-analysis

### Modular LCA
An approach for modular LCA. Parts of lifecylces can be recombined in flexible ways. This can also be used to make lifecycle stages and simply calculate the environmental impact of these. A graphical user interface is very useful (but currently only a very early version of the Activity Browser contained this; a new interface may be added in the future).

https://github.com/bsteubing/modular-lca
