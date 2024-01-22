# Exploration of [DesignSpark](https://www.rs-online.com/designspark/home) Mechanical CAD
* DesignSpark Mechanical (Version 6) [just became available in January 2023](https://www.eejournal.com/industry_news/rs-unveils-next-phase-of-designspark-engineering-community-offering-enhanced-and-personalised-resources/).
    * According to Wikipedia, "DesignSpark Mechanical is based on the SpaceClaim Engineer application and is the product of a collaboration between RS Components and Ansys, Inc."
    * Earlier versions of DesignSpark have been *free* but have had some "add-on" options ($) available to make it more useful.
    * I do remember looking at it at version 4, and thinking that it came up short of my needs.
    * **Not any more**. Version 6 is now a fully capable stand-alone professional CAD application.
* Signed up for 7-day free trial of CREATOR Plan ($12/mo) 
* Registered and created an account
    * Used my email as username
* Downloaded & installed on Windows 10
* This [10-minute "Gee Whiz" video](https://www.youtube.com/watch?v=ZXgMY3-hlgs) (by a former Solid Works user) showcases some of the amazing power of DS Mechanical

## Learning to use DesignSpark Mechanical

### [The "official" DesignSpark Mechanical Video Tutorials](https://www.youtube.com/watch?v=XyuzbKSCO90&list=PLv91f6GOku1_q3UNIORWX2ByS4g_1kknk)
* Series of 11 video tutorials
* Total time: 43 minutes

### [DSM Online Help](https://help.spaceclaim.com/dsm/6.0/en/index.html)

### [DesignSpark Mechanical tutorials](https://www.rs-online.com/designspark/creating-your-mechanical-3d-design)

### Other Video Tutorials
* Collection of [47 video tutorials from RS DesignSpark](https://www.youtube.com/playlist?list=PLv91f6GOku1_WEeZMDmspEx0ZC-odebsR) (This is an older collection, with some up to 9 years old)
* The MakerHive DesignSpark Mechanical - ZERO TO HERO [EPISODE 1](https://www.youtube.com/watch?v=WYcAZVgKWPA) shows some efficient *Best Practices*
* Best Practice: Components & Assemblies [DesignSpark Mechanical - How to - Creating components](https://www.youtube.com/watch?v=DBfSRpKoZYo)
* Basics of components & Assemblies. Also: copies vs. Instances [Understanding structure tree in SpaceClaim](https://discoveryforum.ansys.com/t/h4pkhk/understanding-structure-tree-in-spaceclaim)
* [The Structure Tree Explained (DSM06)](https://www.youtube.com/watch?v=5ynwr-laInM) (one in a series) Explains structure tree in detail
    * Produced by [Fabrication Planet Channel](https://www.youtube.com/@fabricationplanet)
    * The entire series of [All 11 videos](https://www.youtube.com/watch?v=WwM3VeYQp9I&list=PLYosAvMmVaJJJytCw-l6gik-_w6bY9B5Y)
* Intricacies of the Move Tool [Translate and rotate items in SpaceClaim using Move tool](https://discoveryforum.ansys.com/t/18pkh6/translate-and-rotate-items-in-spaceclaim-using-move-tool)
* Move a component so that its face is in alignment to another face [DesignSpark Mechanical - How to Align Object Up To](https://www.youtube.com/watch?v=sLYYv_BHJUo)

### How To make Detailed Drawings:
* Start by **right clicking a component** (part or assembly) in the assembly tree
    * Select *Open Component*
    * Click *File* -> *New* -> *Drawing Sheet*
* Watch [Detailing Tutorial](https://www.youtube.com/watch?v=fd5MbU-f2tk) for all the detailed instructions

### How to Mate and Align Components
* [Mate & Align tutorial](docs/mate&align.md)

### **Shared** versus **Copied** parts and assemblies
* Different CAD vendors use different terminology, so this can get confusing. To keep it as simple as possible, I will restrict this discussion to the two Dynamic CAD applications:
    1. SolidDesigner (PTC Creo Elements Direct)
    2. SpaceClaim (DesignSpark Mechanical)
* Although PTC has the formidable task of maintaining both their legacy history-based CAD product (Pro-Engineer) as well as their more recently acquired Direct Modeling CAD product (Creo Elements Direct), their article [About shared parts and assemblies](https://support.ptc.com/help/creo/ced_modeling/r20.6.0.0/en/index.html#page/ced_modeling/OSDM_Main/Parts_C_9.html) does a good job of summing up the difference between *share* and *copy* as it applies to parts and assemblies. (This same distinction also applies in SpaceClaim, but SpaceClaim prefers to use the term *components* rather than *parts*.)

> It is recommended to use the *Share* functions in preference to the *Copy* functions for any parts and assemblies which are used more than once in a model. By sharing parts, you ensure that modifications made to one shared part are automatically reflected in all other shared instances of that part.
> When sharing parts or assemblies, the largest proportion of data, particularly data concerned with the geometry of a part, is shared between all instances. Consequently, this shared data exists only once in memory.
> Shared assemblies share the same parts and information about the relationship between the parts; for example, positioning of parts within the assembly.

* Toward the end of the SpaceClaim video [Basics of components & Assemblies](https://discoveryforum.ansys.com/t/h4pkhk/understanding-structure-tree-in-spaceclaim) they show how components behave if they are *copied* versus if they are *shared*. But SpaceClaim doesn't use the same terminology. Instead, they explain that it is a *best practice* when copying, to not copy a solid directly, but instead, to copy the component which contains it. This way, the copied solid will be linked to the original so that when one is modified, the other is also modified. (In other words, they are *shared*.) If you prefer to *break* that shared relationship, you can right-click on the newly copied component and then click *Source* then *Make independent*.

* Best practice in SpaceClaim is to treat assemblies the same way. Copying the assembly creates what is effectively a *shared* instance of the original assembly. Any change in one assembly (such as a moved component) would occur in the other assembly. If you want to break the shared relationship, you do it the same way: right click the newly copied assembly, then click *Source* then *Make independent*. But be aware that this is a **deep copy**, meaning that every last component and subassembly loses its shared relationship with the original. That's probably not what you want to do.
    * There is a small (but annoying) issue when making a shared copy of an assembly in DesignSpark Mechanical. Say you have an assembly on the left and you want to have an identical (shared) assembly on the right. Well, you can't give them different names. If you want them to show up in the assembly tree as *assy-left* and *assy-right*, then you have to create two new parent components with those names and then drag and drop the respective assemblies into them.

----------------------------------------------------
## Appendix
### CAD kernel Primer
* There are 2 distinctly different types of CAD modeling kernel
    1. **History-based** (sometimes called **Parametric**) modeling kernel is relatively **primitive**
        * It keeps track of a *recipe* or *history* of every individual *primitive* step used in the creation of each solid body or part in the overall assembly.
        * In order to make changes to a part requires the user to edit its history
            * By first studying the sequence of steps in the history, then
            * modifying parameters used at various steps, or
            * re-ordering the steps or
            * both.
        * Pretty much **all** CAD applications in use today have a history- based modeling kernel.
    2. **Dynamic** (sometimes called **Direct**) modeling kernel is more **sophisticated**
        * It keeps track of the *resulting shape* of each solid body, irrespective of the steps taken to arrive at this result.
        * To enable the user to edit shapes, the modeling kernel must be much more sophisticated.
            * Implementing such a dynamic modeling kernel is a difficult technical challenge.
            * But the benefit is a greatly improved user experience.
            * The user is able to modify parts without getting bogged down in the details of all the steps that went into the part's creation.
            * The kernel takes care of all those details by recalculating all the *edges* where the modified face intersects any adjacent faces, replacing the original shape with the edited shape.
        * By contrast, there are very few CAD applications that use a dynamic modeling CAD kernel
            1. Hewlett-Packard ME30 was the first. According to [The CAD Insider](https://www.thecadinsider.com/2007/10/cocreate-follow.html), ME30 dates back to the 1980s when HP developed its own CAD system for use by its own engineeers. Their engineers wanted a CAD application that was easier and more intuitive to use. The engineers **loved** it so much that HP began to make it available outside HP as ME10 (for 2D) and ME30 (for 3D). By 1995, the name was changed to [SolidDesigner](https://www.hpl.hp.com/hpjournal/95oct/oct95a1.pdf), the world's first Dynamic Modeling CAD application.
                * Spun off as CoCreate (in 2000), then bought by PTC (in 2007). Now sold as [Creo Elements/Direct Modeling](https://www.ptc.com/en/products/creo/elements-direct)
                    * PTC offers a **free version** called [Creo Elements/Direct Modeling Express](https://www.ptc.com/en/products/creo/elements-direct/modeling-express), intended to give the user a taste of *how it works* but with [restricted fuctionality](https://www.ptc.com/-/media/Files/PDFs/CAD/Creo/37318-CED-Topic-Sheet-assets-1.pdf):
                        * Will handle assemblies up to a maximum of 60 unique parts
                        * Can load STEP files, but cannot save in STEP format

            2. [SpaceClaim](https://en.wikipedia.org/wiki/SpaceClaim), initially introduced in 2007
                * Purchased by Ansys in 2014
                    * Still available within the Ansys suite of engineering simulation tools
                    * Licensed to RS Components and made available as [DesignSpark Mechanical](https://www.rs-online.com/designspark/mechanical-software), a stand-alone CAD product
                    * Starting in 2023, with the release of version 6, DesignSpark Mechanical was made available with a choice of 2 subscription plans:
                        * *Explorer* (free) does not allow load/save in STEP format
                        * *Creator* ($12/mo) allows loading/saving in STEP format

### Why does the CAD kernel matter?

* It matters to the user.
    * With **History based CAD**, the user ends up having to do tedious errands the CAD tool should be doing.
        * Creating and editing models is more **tedious** than it needs to be
        * The user interface is more complicated, as it must display the history of all modeling steps and allow that history to be edited and the CAD geometry to be regenerated. 
        * Longer learning curve.
    * By contrast, a **Dynamic Modeling CAD** allows the designer to work intuitively, and stay focused on the design job.
        * Simpler and easier to **learn**
        * Simpler and easier and **way more FUN to use**
        * Facilitates easier, faster prototyping
        * Design changes are a breeze
> Always choose high quality tools, not only because they will help you do a job faster, easier, safer and better, but because they are a joy to use.

