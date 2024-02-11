# The 2 basic CAD kernel types
* **History-based**
* **Dynamic**

## Why does the CAD kernel matter?

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

## Drilling down into the differences
* A **History-based** (sometimes called **Parametric**) modeling kernel is relatively **primitive**
    * It keeps track of a *recipe* or *history* of every individual *primitive* step used in the creation of each solid body or part in the overall assembly.
    * In order to make changes to a part requires the user to edit its history
        * By first studying the sequence of steps in the history, then
        * modifying parameters used at various steps, or
        * re-ordering the steps or
        * both.
    * Pretty much **all** CAD applications in use today have a history- based modeling kernel.
* A **Dynamic** (sometimes called **Direct**) modeling kernel is more **sophisticated**
    * It keeps track of the *resulting shape* of each solid body, irrespective of the steps taken to arrive at this result.
    * To enable the user to edit shapes, the modeling kernel must be much more sophisticated.
        * Implementing such a dynamic modeling kernel is a difficult technical challenge.
        * But the benefit is a greatly improved user experience.
        * The user is able to modify parts without getting bogged down in the details of all the steps that went into the part's creation.
        * The kernel takes care of all those details by recalculating all the *edges* where the modified face intersects any adjacent faces, replacing the original shape with the edited shape.
    * By contrast, there are very few CAD applications that use a dynamic modeling CAD kernel

## Historical perspective

> Some important pioneering development went into the creation of the first **Dynamic** kernel.

* Hewlett-Packard ME30 was the first CAD application to use a dynamic kernel. According to [The CAD Insider](https://www.thecadinsider.com/2007/10/cocreate-follow.html), ME30 dates back to the 1980s when HP developed its own CAD system for use by its own engineeers. HP engineers asked for a CAD system that was more intuitive and easier to use than the klunky CAD systems available to them at the time. HP-MDD (Mechanical Design Division) was chartered to get this done. They started out using the ACIS kernel. They asked ACIS to make modifications in their kernel that would enable users to modify the shapes of their models by moving faces. The ACIS developers weren't able to provide what they needed , so the HP-MDD developers were left with the task of figuring it out on their own. They succeeded. The engineers **loved** their new CAD so much that HP began to make it available outside HP as ME10 (for 2D) and ME30 (for 3D). By 1995, the name was changed to [SolidDesigner](https://www.hpl.hp.com/hpjournal/95oct/oct95a1.pdf), the world's first Dynamic Modeling CAD application.
    * Spun off as CoCreate (in 2000), then bought by PTC (in 2007). Now sold as [Creo Elements/Direct Modeling](https://www.ptc.com/en/creo/elements-direct)
        * PTC offers a **free version** called [Creo Elements/Direct Modeling Express](https://www.ptc.com/en/products/creo/elements-direct/modeling-express), intended to give the user a taste of *how it works* but with [restricted fuctionality](https://www.ptc.com/-/media/Files/PDFs/CAD/Creo/37318-CED-Topic-Sheet-assets-1.pdf):
            * Will handle assemblies up to a maximum of 60 unique parts
            * Can load STEP files, but cannot save in STEP format

* [IronCad](https://www.ironcad.com/), initially released in 1998, also permits dynamic modifications. It has some pretty cool functionality for creating components (such as gears) which allow the user to click on some basic parameters and generate the component. IronCAD claims to be the only CAD solution with dual kernels (PARASOLID and ACIS) for greater import/export versatility and the ability to switch or use both while modeling.

* A third CAD system based on a dynamic modeling kernel, [SpaceClaim](https://en.wikipedia.org/wiki/SpaceClaim), was initially introduced in 2007
    * Purchased by Ansys in 2014
        * [Ansys SpaceClaim](https://www.ansys.com/products/3d-design/ansys-spaceclaim) is available for free trial but I didn't download it and try it.
        * Also available as part of a [Free Ansys Student package](https://www.ansys.com/academic/students). I downloaded & installed [Ansys Student 2024 R1](https://www.ansys.com/academic/students/ansys-student). It is **Huge** requiring 88 GB Disk space. Once installed, I discovered that Cad designs cannot be saved in STEP format, only in native `.scdoc` format.
        * Licensed to RS Components and made available as [DesignSpark Mechanical](https://www.rs-online.com/designspark/mechanical-software), a stand-alone CAD product which installs in < 3GB of disk space.
        * Starting in 2023, with the release of version 6, DesignSpark Mechanical was made available with a choice of 2 subscription plans:
            * *Explorer* (free) does not allow load/save in STEP format
            * *Creator* ($12/mo) allows loading/saving in STEP format


