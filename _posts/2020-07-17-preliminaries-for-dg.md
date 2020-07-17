---
toc: true
layout: post
title: Preliminaries for Differential Geometry
description: Mathematical concepts preliminary for Differential Geometry
categories: differential-geometry
comments: true
image: images/dg/dg01.png
---
This post will discuss the mathematical preliminaries for starting off into [Differential Geometry](https://en.wikipedia.org/wiki/Differential_geometry "Differential Geometry, Wikipedia")
<hr>
## Categories and Functors

### Category
A Category $$\mathcal{C}$$ consists of
+ A Class of **objects** $$\text{Ob}_{\mathcal{C}}$$
+ A set of **morphisms**[^1] $$\text{Mor}_{\mathcal{C}}(A,B)$$ for any two objects $$A, B \in Ob_{C}$$
+ A **composition operation** $$\text{Mor}_{\mathcal{C}}(X,Y) \times \text{Mor}_{\mathcal{C}}(Y,Z) \to \text{Mor}_{\mathcal{C}}(X,Z)$$ or $$(f,g)  \mapsto g \circ f$$ for any morphisms 


[^1]:Also known as **maps** or **arrows**