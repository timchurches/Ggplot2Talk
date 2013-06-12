---
title       : ggplot2
subtitle    : grammar for graphics
author      : Tim Churches
job         : The Sax Institute, Sydney, Australia
logo        : Rlogo.png
biglogo     : saxinstitute_logo.png
license     : by-nc-sa
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {selfcontained, standalone, draft}

--- 

## source
The majority of the material in this presentation is borrowed from:
- Hadley Wickham. _ggplot2: Elegant Graphics for Data Analysis_ Springer:2009 DOI 10.1007/978-0-387-98141-3
- ![Hadley Wickham](assets/img/hadley_wickham.jpg)
- ggplot2 documentation: http://docs.ggplot2.org/current/

This presentation was created using ```slidify``` for R - see http://slidify.org
- the Markdown source code for these slides, including the embedded R code, is available at https://github.com/timchurches/Ggplot2Talk




---

## grammar of graphics

Wilkinson (2005) created a grammar of graphics to describe the deep features that underlie all statistical graphics as "parts of speech": 
   >- The ```data``` that you want to visualise
   >- An aesthetic mapping, ```aes``` for short, describing how variables in the data are mapped to aesthetic attributes that you can perceive
   >- geometric objects, ```geoms``` for short, representing what you actually see on the plot: points, lines, polygons, etc
   >- optional statistical transformations, ```stats``` for short, summarising data in many useful ways, e.g.
      - binning and counting observations to create a histogram
      - summarising the relationship between two variables with a linear model

---

## grammar of graphics

   >- a coordinate system, ```coord``` for short, describing how data coordinates are mapped to the plane of the graphic
      - also provides axes and gridlines to make it possible to read the graph
      - a Cartesian coordinate system, but a number of others are available, including polar coordinates and cartographic map projections
   >- ```scales``` which map values in the data space to values in one or more aesthetic spaces
      - indicate position in Cartesian or other 2-dimensional projections
      - encode values as colour, size or shape of symbols, lines
      - ```scales``` draw labelled axes and/or a legend
      - provide a reverse mapping to make it possible to read the original data values from the graph
   >- a ```facet``` specification describing how to break up the data into subsets and how to display those subsets as and arrangement of small multiples
    - known as conditioning or latticing/trellising ("panelling" in the Lattice package) 

---

## anatomy of a plot

![plot anatomy](assets/img/ggplot2-anatomy-all-annotated.png)

Graphic by Software and Programmer Efficiency (Sape) Research Group at the Faculty of Informatics of the University of Lugano

---

## grammar not pronounciation

   >- the Wilkinson grammar of graphics does not include finer points of display
      - font size or background colour are not specified by the grammar
      - such attributes are analogous to pronounciation (or maybe typography?)
  
   >- ggplot2 specifies such attributes with a ```theming``` system
      - the default theme is very attractive, and thoughtfully designed
      - alternative themes come with the package
      - easy to tweak themes or design your own

   >- ggplot2 maintains a clean separation between:
      >- the ```data``` to be visualised
      >- the form of that visualisation (defined by the ```grammar```)
      >- how the rendered graphic looks (defined by the ```theme```)

---

## what ggplot2 doesn't do

   >- graphs are static, not interactive (e.g. brushing, zooming), but...
      - Hadley Wickham is rewriting ggplot2 in JavaScript, using the d3 library -> interactive graphs
      - the incremental, object-oriented nature of ggplot2 graphs make them ideal targets for interactive graph specification via Shiny or similar
   >- 3D graphics (cf lattice package for R)    
   >- exhaustive comparison of lattice vs ggplot2 capabilities and results in 12 parts at:
      - http://learnr.wordpress.com/2009/06/28/ggplot2-version-of-figures-in-lattice-multivariate-data-visualization-with-r-part-1/
      - ...through to...
      - http://learnr.wordpress.com/2009/08/18/ggplot2-version-of-figures-in-lattice-multivariate-data-visualization-with-r-part-13/

---

## ggplot2 versus other R graphics systems

>- base graphics in R
    - written by Ross Ihaka, University of Aukland, based on S graphics driver
    - use a pen-on-paper model: you can only draw on top of the plot, you cannot modify or delete existing content
    - no (user accessible) representation of the graphics, apart from their appearance on the screen
    - includes both tools for drawing primitives and entire plots.

>- grid graphics, a much richer system of graphical primitives, written in 2000 by Paul Murrell, also at University of Auckland
    - grid ```grobs``` (graphical objects) can be represented independently of the plot and modified later
    - viewports (each containing its own coordinate system) makes it easier to lay out complex graphics
    - provides drawing primitives, but no tools for producing statistical graphics

---

## ggplot2 versus other R graphics systems

>- lattice package, developed by Deepayan Sarkar, uses grid graphics to implement the trellis graphics system of Bill Cleveland (1985)
    - easily produce conditioned plots
    - some plotting details (e.g., legends) taken care of automatically
    - but lacks a formal model, which can make it hard to extend (custom panel functions can be tricky to write)

>- ggplot (precursor to ggplot2), also developed at University of Auckland!
    - also uses grid graphics for underpinnings
    - formal grammar
    - far more modular and object-oriented
    - strong separation of data, grammar and themes

---
  
## installing ggplot2











































































































































