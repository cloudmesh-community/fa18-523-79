# QlikView :smiley: :exclamation: fa18-523-79

| Abhishek Rapelli
| arapelli@iu.edu
| Indiana University
| hid: fa18-523-79
| github: [:cloud:](https://github.com/cloudmesh-community/fa18-523-79/blob/master/paper/paper.md)

## Keywords

HID fa18-523-79, QlikView, Associative In-Memory Technology, QlikView Server, QlikView Publisher

## Introduction

QlikView is a popular software that was based on different approach for data discovery and analytics compared to other traditional analytical and visualization software tools. The uniqueness of QlikView is that rather than first building a query and then fetching the results, it forms associations in the data once it is loaded and then the user is prompted to explore and analyze the data with. This simplification of data exploration and the enhanced user interface has made it one of the most popular choice for traditional business analytics and reporting for businesses. QlikView, besides QlikSense is one of the software tools that was developed and maintained by Qlik software technologies company for Business Intelligence, analytics and visualization. Over the years, with more advancements and simplifications in BI tools, QlikView has gained its prominence for small to medium scale business analytics applications due to its simplicity, easiness and handiness. It adapted to the changes in the BI tools experience that businesses and Industries wanted, like for example Predictive analytics ability, advanced visualization and smart suggestions. Majority of the business analytical tasks require routine reporting and dashboard creation for presentation to managers, which is most times very repetitive and mundane. QlikView makes such work much simpler and easy for them [fa18-523-79-Wikipedia].

## Architecture

Before moving forward to deploy and use QlikView software, it is very much important to understand the architecture of QlikView, its products and the components. The QlikView deployment has three main infrastructure components. They are QlikView Developer (QVD), QlikView Server (QVS) and QlikView Publisher (QVP). The QVD is a desktop application for Windows operating system for designers and developers for performing operations like data retrieval, storage and processing, and also to make graphical user interface (GUI). The QVS is a component that handles the interaction or communication between the clients and QlikView applications and components. It also loads QV applications into the main memory and helps in running the user selections. The QVP is collects and loads the data from various sources, in different formats ranging from XML to CSV. It also reduces the QV application and then distributes the data to the QVS server. It is always good to separate the two components of QVS and QVP, since both function differently, handle the memory and CPU differently and have completely different roles [fa18-523-79-Quora-Answer-number-4].

Broadly speaking, QlikView’s architecture can be viewed as the combination of two main components. They are the front end and the back end. The front end’s function is to visualize the processed data whereas the back end’s function is to provide security and publication mechanism for the new user documents. 

## The Front End

The front is the component that facilitates users to interact with the data and documents stored for data processing through the QlikView server, anywhere and at any time. The QlikView Publisher in the back end creates QlikView documents of the user, which are contained in the QlikView server of the front end. These files are stored in the formats of QVW, meta, and shared. The interaction or communication between the user or client and the server is managed through HTTPS, or QlikView Proprietary, also called QVP protocol. The QlikView server also handles the security of the client.
 
## The Back End

The back end is the inner component of the QlikView where the QlikView documents that are created by using QlikView Developer are stored and protected. The files can be script documents for data extraction from various sources like SQL scripts, the data that is in binary form and stored within the QVD files. The most important component of the back end is the QlikView Publisher, which is responsible loading and distribution of data. The back end functions within the windows environment and required special privileges and permissions for its functioning. 

## Associative In-Memory Technology

Associative In-Memory technology is used by QlikView for the analyzing and processing the data. The advantage of this technology is that it stores only unique entries at a time in the memory and rest all are pointers to the main data. This makes it very fast and allows to store large amounts of data than other traditional methods. The performance and scaling is key to QlikView as the user is directly connected to the CPU of the QlikView, and hence this technology is used for speed and scaling.

The QlikView’s System resources consists of computation components like CPU, RAM, etc. The QlikView Server and QlikView Publisher are the two components that use and handle these resources differently as they serve different purposes and exhibit different roles. Let us look at how these two utilize and handle these resources.

## QlikView Server (QVS)

### CPU

The QlikView Server consists of multiple CPU cores that are multi-threaded and optimized. The available cores are used linearly for processing the QV files. The QVS manages the usage of these cores for computation of these files on real-time basis by monitoring and allocating the cores efficiently. It leverages the processor for dynamic aggregation creation quickly and shows the results to the end user intuitively. Typically, the actual data that is stored in the memory or RAM is in unaggregated raw form. Thus, to perform aggregation operation on real-time bases very quickly on huge sets of data, efficient and dynamic use of computing power is needed. If the processing power is not sufficient, it may lead to waiting and the processes are done based on priority, where a waiting list is created for allocation to the cores based on priority and cores availability. This is a linear and sequential processing model.

### Memory

The QlikView documents and files are stored in the main memory RAM, which is the primary storage for all files. The data that is stored in the RAM can either be in unaggregated form or aggregated form. QlikView memory is based on Snapshot technology, where it is continuously refreshed through a process known as reloading a QlikView document. As the QlikView document is loaded, it will establish connectivity to the data sources that are to be analyzed and the unaggregated data to be extracted and for compression, which is then stored as .QVW format in the persistent disk storage.

When a user opens an analytical application, QlikView loads the .QVW file from the persistent disk storage into the RAM. Further, QlikView only relies on the dataset that is loaded into the RAM at that time and does not care about the other data in the database. This is done because QlikView would be able to handle the process quickly, resulting in instantaneous real time response to the end user. Thus, all the data that has to be processed is placed in the RAM. RAM is the important deciding factor for QlikView about how much data it can handle at once. A Windows Operating System will consume a RAM of 500 to 1000 MB, while QlikView Server process requires a RAM of at least 100 MB on QVS.exe process.

### Data Compression

For effective usage of RAM and quicker real time processing, we need to forgo redundant and repeating data. This can be achieved by loading on distinct data points into the RAM instead of all the data points. This not only reduces the RAM usage and scales up to accommodate huge dataset but also makes the process very quick due to non-redundancy in the dataset. This process of reducing the data points is called Data Compression and is handled by the QlikView server. 

## QlikView Publisher

### CPU

QlikView Publisher is a database load engine and it creates thread for every database connection to facilitate hundred percent utilization of cores during processing. The number of cores being utilized for a process is equal to the number of databases being loaded for the process. The QVS and QPS are not placed on the same server because both use and handle CPU cores in different way as explained earlier. 

### Hard Drive

The QlikView creates a data repository of historical data that the end users have loaded from various applications. This is also known as data cache. The main advantage of this kind of data model is that it reduces the database communication and reduces the time lag. The main disadvantage of this is that the disk space needed to source files is very high. It is recommended to have at least 150 GB space of SAN drive.

### Memory

As we noted earlier, as QlikView Publisher is a database load engine and a file distribution service. It is not just an analytics service engine. Compared to the QlikView Server, QlikView Publisher is not memory intense and hence memory is not a consideration or a factor for determining the size of the service to accommodate huge QlikView Publisher instances [Qlikview-architecture-documentation].

## Uses and advantages

QlikView is widely used by businesses for Business Intelligence, analytics, visualization and reporting task to monitor business performances on daily, weekly, month, quarterly or yearly basis. It can be used both for on-site reporting as well as client-side remote reporting on real time through internet. Hence, it can be accessed at any time or anywhere through internet. From user point of view, it is very simple and conformable UI, that is drag and drop based and hence not at all difficult or hard to master and operate quickly. The reports and visualizations can be interactive, which makes it feel good and easy for understanding to the viewer. All these advantages make it one of the most preferred BI tools in the industry [fa18-523-79-QlikView-Tutorial].

## Conclusion

QlikView being a web-based software tool is very simple, reliable and robust and access-able for various BI applications. It is easy to learn, work on and present compared to traditional software available in this segment. Yet, it has got lot of short coming too, where it cannot be used for large scale data analytics like Big-Data and it does not support advanced machine learning based predictive analytics. However, for small to medium-large level data sets, it is one of the best software that is available for business analytics and visualization tasks.
