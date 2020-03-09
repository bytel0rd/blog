+++
author = "abiodun oyegoke"
title = "Sharing Through Typescript (3.8) type Keyword"
date = "2020-03-11"
description = "How to easily share typescript type information and code easily across mutiple projects"
tags = ["Typescript", "NodeJS", "folder Structure"]
categories = ["Typescript"]
images  = ["https://cdn.pixabay.com/photo/2014/11/22/17/58/clasped-hands-541849_960_720.jpg"]
type = "post"
+++
## Sharing Through Typescript (3.8) type Keyword.

Typescript is one of my favorite tools which delivers on its promise which has made JavaScript development easy and fun. Typescript type checking and easy feedback with the language server for various IDE's has been a bliss. Typescript's ability to share type information across projects has been a bliss especially in big-medium size projects but it has also born a desire the need to share type information only which had been a dauting task especially if has to be collated across sub modules until the \*\*type\*\* keyword was born. An example would be sharing type information between a react frontend and a NodeJS backend written in typescript. Using the example has a case study I will demonstrate various approaches I have taken before and also after the type keyword was introduced.

### Before:

The way I structure code and type information that needed to be shared was segmented into two approaches which are:

1.  Environment based approach.

2.  Context based approach.

Irrespective of my approach without the __type__ keyword, I can't export type information only but can share code which I don't want to prevent unwanted dependency.

#### Environment Based Approach.

This approach suggested that the code should be separated depending on the environments that they run such that for our example's case, the project would have three different folders, which are:

-   Platform shared: This folder contains files which are subset of modules actually shared by both the browser and NodeJS. This folder restricts the importing of native NodeJS and browser Window based modules, since window properties doesn't exit in NodeJS and native modules are also missing from the browser. This folder also restricts importing one-sided used imports such that if it's not used by both, it's not wanted there.

-   Web: This folder contains the react source code and imports the platform shared and has no interaction with the Server folder.

-   Server: This folder contains native modules and the server business logic itself, it imports the platform-shared and has no interaction with the web

> The platform shared folder is transpiled to JavaScript and symlink using ```yarn link``` command and utilized using {name} which is in the folder __package.json__.

#### Context Based Approach.

This approach suggest that the code should be group and located in the same folder instead of mirroring modules structure in the environment approach. This style doesn't remove the code from their context and can be reason about easily. Using our example as a case study again, the base folder would be two, the structure is shown below:

-   NodeJS: This folder contains multiple sub modules used by NodeJS, all the sub modules will have a file called frontend.ts which collates all the exported properties from them. The sub modules also have a folder called frontend but exports other modules frontend.ts files. The frontend folder is transpiled and symlink like the platform shared above.

-   Web: This folder contains the client source files and imports the frontend folder module name.

### After:

Since the type keyword now exists in typescript 3.8 and we can now iterate on the context and environment-based approach by mixing them. We can drop unwanted code exporting with type keyword selectively instead of using \* for the target module or file. If there are some code, we wish to export, we will separate it to a file which can be exported meaning inside our context-based structure, when we fundamentally export, we do it with environment-based approach.

## Summary.

The type keyword gives as a flexibility to export type information irrespective of environments and allow easier collation of type information across modules.