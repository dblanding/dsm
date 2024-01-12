# Exploration of [DesignSpark](https://www.rs-online.com/designspark/home) Mechanical CAD
* DesignSpark Mechanical (Version 6) [just became available in January 2023](https://www.eejournal.com/industry_news/rs-unveils-next-phase-of-designspark-engineering-community-offering-enhanced-and-personalised-resources/).
    * According to Wikipedia, "DesignSpark Mechanical is based on the SpaceClaim Engineer application and is the product of a collaboration between RS Components and Ansys, Inc."
    * Earlier versions of DesignSpark have been *free* but have had some "add-on" options ($) available to make it more useful.
    * I do remember looking at it about 5 years ago and thinking that it came up short of my needs.
    * **Not any more**. Version 6 is now a fully capable stand-alone professional CAD application.
* Signed up for 7-day free trial of CREATOR Plan ($12/mo) 
* Registered and created an account
    * Used my email as username
* Downloaded & installed on Windows 10
* This [10-minute "Gee Whiz" video](https://www.youtube.com/watch?v=ZXgMY3-hlgs) (by a former Solid Works user) showcases some of the amazing power of DS Mechanical

## Tutorials on learning to use DesignSpark Mechanical
* [The "official" DesignSpark Mechanical Video Tutorials](https://www.youtube.com/watch?v=XyuzbKSCO90&list=PLv91f6GOku1_q3UNIORWX2ByS4g_1kknk)
    * Series of 11 video tutorials
    * Total time: 43 minutes
```
1
1:09
DesignSpark Mechanical Training | 0 Introduction
RS DesignSpark
2
6:01
DesignSpark Mechanical Training | 1 Familiarisation
RS DesignSpark
3
2:27
DesignSpark Mechanical Training | 2 Sketching
RS DesignSpark
4
5:31
DesignSpark Mechanical Training | 3 Edges
RS DesignSpark
5
4:25
DesignSpark Mechanical Training | 4 Cut-outs
RS DesignSpark
6
3:08
DesignSpark Mechanical Training | 5 Importing
RS DesignSpark
7
4:23
DesignSpark Mechanical Training | 6 Manipulating
RS DesignSpark
8
3:24
DesignSpark Mechanical Training | 7 Combining
RS DesignSpark
9
2:33
DesignSpark Mechanical Training | 8 Dimensions
RS DesignSpark
10
4:14
DesignSpark Mechanical Training | 9 Positioning
RS DesignSpark
11
3:50
DesignSpark Mechanical Training | 10 Threads
RS DesignSpark
```
* The MakerHive DesignSpark Mechanical - ZERO TO HERO [EPISODE 1](https://www.youtube.com/watch?v=WYcAZVgKWPA) shows some efficient *Best Practices*
* Best Practice: Components & Assemblies [DesignSpark Mechanical - How to - Creating components](https://www.youtube.com/watch?v=DBfSRpKoZYo)
* Basics of components & Assemblies. Also: copies vs. Instances [Understanding structure tree in SpaceClaim](https://discoveryforum.ansys.com/t/h4pkhk/understanding-structure-tree-in-spaceclaim)
* [The Structure Tree Explained (DSM06)](https://www.youtube.com/watch?v=5ynwr-laInM) (one in a series) Explains structure tree in detail
    * Produced by [Fabrication Planet Channel](https://www.youtube.com/@fabricationplanet)
    * The entire series of [All 11 videos](https://www.youtube.com/watch?v=WwM3VeYQp9I&list=PLYosAvMmVaJJJytCw-l6gik-_w6bY9B5Y)
* Collection of [47 video tutorials from RS DesignSpark](https://www.youtube.com/playlist?list=PLv91f6GOku1_WEeZMDmspEx0ZC-odebsR) (This is an older collection, with some up to 9 years old)
----------------------------------------------------

## Overview of the 2 basic types of CAD kernel
* There are 2 distinctly different types of CAD modeling kernel
    1. **History-based** (sometimes called **Parametric**) modeling kernel is relatively **primitive**
        * It keeps track of a *recipe* or *history* of every individual *primitive* step used in the creation of each solid body or part in the overall assembly.
        * In order to make changes to a part requires the user to edit its history
            * By first studying the sequence of steps in the history, then
            * modifying parameters used at various steps, or
            * re-ordering the steps or
            * both.
        * Almost all CAD applications use a history based modeling kernel.
    2. **Dynamic** (sometimes called **Direct**) modeling kernel is more **sophisticated**
        * It keeps track of the *resulting shape* of each solid body, irrespective of the steps taken to arrive at this result.
        * To enable the user to edit shapes, the modeling kernel must be much more sophisticated.
            * Implementing such a dynamic modeling kernel is a difficult technical challenge.
            * But the benefit is a greatly improved user experience.
            * The user is able to modify parts without getting bogged down in the details of all the steps that went into the part's creation.
            * The kernel takes care of all those details by recalculating all the *edges* where the modified face intersects any adjacent faces, replacing the original shape with the edited shape.
        * To my knowledge, only 2 dynamic modeling CAD kernels exist.
            1. [SolidDesigner](https://www.hpl.hp.com/hpjournal/95oct/oct95a1.pdf), initially developed around 1990 by Hewlett-Packard. HP had an in-house project team located in Sindelfingen, Germany whose goal was to develop a dynamic modeling kernel for a new and improved CAD application to be used by HP design engineers. Initially, this CAD application was known as HP PE/ME30. HP continued to develop it and by 1995, they began to market it as [SolidDesigner](https://www.hpl.hp.com/hpjournal/95oct/oct95a1.pdf), the world's first (and only) Dynamic Modeling CAD application.
                * Spun off as CoCreate (in 2000), then bought by PTC (in 2007). Now sold as [Creo Elements/Direct Modeling](https://www.ptc.com/en/products/creo/elements-direct)
                    * PTC has a free version called [Creo Elements/Direct Modeling Express](https://www.ptc.com/en/products/creo/elements-direct/modeling-express) but it is limited to a maximum of 60 parts and can only be saved in a native file format. (not STEP)
            2. [SpaceClaim](https://en.wikipedia.org/wiki/SpaceClaim), initially introduced in 2007
                * Purchased by Ansys in 2014
                    * Still available within the Ansys suite of engineering simulation tools
                    * Licensed to RS Components and made available as [DesignSpark Mechanical](https://www.rs-online.com/designspark/mechanical-software), a stand-alone CAD product

## Why does it matter?
* It matters to the user.
    * With **History based CAD**
        * Creating and editing models is more tedious than it needs to be
        * The user interface is more complicated, as it must display the history of all modeling steps and allow that history to be edited and the CAD geometry to be regenerated. 
        * Longer learning curve.
    * By contrast, **Dynamic Modeling CAD** is
        * Simpler and easier to **learn**
        * Simpler and easier to **use** (It's actually **fun** to use)
        * Facilitates easier, faster prototyping

