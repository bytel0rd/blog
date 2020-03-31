+++
author = "abiodun oyegoke"
title = "Growing Micro at scale"
date = "2020-03-31"
description = "How to build a scalable system from ground up with little comlexity"
tags = ["Architecture", "mircoservices"]
categories = ["Architecture"]
type = "post"
+++
<!-- images  = ["https://cdn.pixabay.com/photo/2014/11/22/17/58/clasped-hands-541849_960_720.jpg"] -->

## GROWING MICRO.
​	Ulmax is a side project for health problems in Africa in general. Ulmax's overall goal is to modernize the healthcare industry has well has increase the quality of health care service delivery by bringing the institutions and clients together. The ulmax project consist of five people namely: *Olakorede wale, Akinrinde Lyida , Oyegoke Abiodun, OLadipupo segun and Oladipupo ismaie.* The first two are nurses while the remaining three are just smart hackers.

​	Ulmax being a relatively newly formed team had an advantaged opportunity to design its technical infrastructures from ground up to accommodate major eventual services load it will later offer has in the road map. The term "micro-services" became a reoccurring term for the ideal nature of such system. The ideal of microservices is such that a system is broken down into smaller independent deployable units while maintenance and replacement can be done without bring down the whole system. The ideal itself is good but the issue with implementing microservices is "context boundaries". Context boundaries are well defined areas of functionalities which a service can serve, the issue with context boundaries for a new system is that the boundaries are non-existent, so designing microservices for an un-existing system is somewhat complicated because domain context in itself at that level is abstract.  

>  ### "A bad plan is better than no plan, at all" 

​	We did design the microservices at a higher level but it was clear we needed to "diverge to converge to diverge" again. The first divergent was to look at the expected services endpoints and speculate a boundary of such, so that has the system converges, it can still be easily separated again without much hassle. As with any architecture it can make a clear picture of functional boundaries i.e. like saying a house will have a living room, three bedrooms with bathrooms and a kitchen. The fundamental less difficult thing to envision are the intangible additions like a flower vase or a book shelf magically appearing like a side-effect of space but it's the unexpected intangibles that makes the whole simple system complicated in real life. The intangibles are part of the evolutionary process of system in general so to migrate across the eventualities of an evolutionary system, it makes it an important decision to choose stacks has a known quantity. Ulmax being an early stage startup with three developers we separate into two product teams, two developers working on a product while am working on a subset of an entire system with a small featured product. The languages selected where C\# Dotnet and Typescript NodeJs, the integration of the two created an overhead which a single language company wouldn't rather have, to converge interfaces we just compiled protobuf definitions without service declaration has the architecture wasn't going to use grpc yet. While the overall surface is an entire system of divergent interfaces but the products also converges a point in which they integrate together and still diverges as a single product functional on their own.

​	The challenges of micro-services pose are quite enormous for a small team with limited engineers, since it incurs its own overhead, the best engineering decision in introduction of complexity such be that the team can handle its load. That means the choices should be to improve and increase developer productivity but might be hinder by future optimizations.