---
toc: true
layout: post
title: Category Theory for Differential Geometry
description: Category Theory quick-start for Differential Geometry
categories: [differential-geometry,category-theory]
comments: true
image: images/math/differential-geometry/dg0.1.png
---
This post is part of a series that will discuss the mathematical preliminaries for starting off into [Differential Geometry](https://en.wikipedia.org/wiki/Differential_geometry "Differential Geometry, Wikipedia")
![]({{site.baseurl}}/images/math/differential-geometry/dg0_1.png "Differential Geometry #0.1")
<hr>

## Categories

A Category $$\mathcal{C}$$ consists of
+ A class of **objects** $$\text{Ob}_{\mathcal{C}}$$
+ A set of **morphisms**[^1] $$\text{Mor}_{\mathcal{C}}(A,B)$$ for any two objects $$A, B \in Ob_{C}$$
+ A **composition operation** $$\text{Mor}_{\mathcal{C}}(X,Y) \times \text{Mor}_{\mathcal{C}}(Y,Z) \to \text{Mor}_{\mathcal{C}}(X,Z)$$ or $$(f,g)  \mapsto g \circ f$$ for any three objects $$X, Y, Z \in \text{Ob}_{\mathcal{C}}$$.
and the following axioms
+ For any four objects $$X, Y, Z, W \in \text{Ob}_{\mathcal{C}}$$ and any morphisms $$ f \in \text{Mor}_{\mathcal{C}}(X,Y), g \in \text{Mor}_{\mathcal{C}}(Y,Z), h \in \text{Mor}_{\mathcal{C}}(Z,W)$$ it is true that

$$ h \circ (g \circ f) = (h \circ g) \circ f$$

+ There exists an unique morphism $$1_{X} \in \text{Mor}_{\mathcal{C}}(X,X)$$ called **identity morphism** such that for any $$f \in \text{Mor}_{\mathcal{C}}(X,Y)$$ and $$g \in \text{Mor}_{\mathcal{C}}(Y,X)$$ the followidng identities hold

$$f \circ 1_{X} = f$$
$$1_{X} \circ g = g$$

A morphism $$f \in \text{Mor}_{\mathcal{C}}(X,Y)$$ is said to be an **isomorphism** if there exists another morphism $$g \in \text{Mor}_{\mathcal{C}}(Y,X)$$ such that $$f \circ g = 1_{Y}$$ and $$g \circ f = 1_{X}$$. Two objects are said to be *isomorphic* if there exists an isomorphism between them. An **endomorphism** is a morphism on the same object, i.e. $$\in \text{Mor}_{\mathcal{C}}(X,X)$$. It is also denoted by $$\text{End}_{\mathcal{C}}(X)$$. A morphism $$f$$ is said to be **automorphic** if it is *both* isomorphic and endomorphic. It is also denoted by $$\text{Aut}_{\mathcal{C}}(X)$$

**EXAMPLE**: **Category of Sets**. The objects are the sets, the morphisms are the maps between sets, the composition operation is the ordinary composition of maps and $$1_{X}$$ is the identity map of $$X$$. Ismorphisms are the bijective maps, and two sets are isomorphic iff they have the same cardinality. Automorphisms are the group of permutations of the elements of the set.

## Diagram
**Diagrams** are Graph Theoretic representation of Categories where each category is assigned a *directed graph*: the vertices represent the objects of the category and the edges represent the morphisms of the category. Any path connecting any two vertices is a morphism (directed along the edge) from one objet to the other. The morphism is given by the composition of the morphisms of the consecutive edges making up the path.

![]({{site.baseurl}}/images/math/category-theory/commutative_diagram.png "Commutative Diagram")

A diagram is said to be **commutative** if, for any two different paths connecting any two vertices, the corresponding morphism is the same. For example, in the above image, if $$f=f_{2} \circ f_1$$ and $$g\circ f=g'\circ f'$$, then the diagram is said to be commmutative.

## Functor

A **Functor** is like an operator between categories which assigns objects of one category to the other and morphisms of one to the other.

### Covariant Functor
**Covariant functor** associates to each object $$X \in \text{Ob}_{\mathcal{C}}$$ an object $$F(X) \in \text{Ob}_{\mathcal{D}}$$, and to each morphism $$f \in \text{Mor}_{\mathcal{C}}(X,Y)$$ a morphism $$F(f) \in \text{Mor}_{\mathcal{D}}(F(X),F(Y))$$ such that
+ identity morphism of any object $$X\in \text{Ob}_{\mathcal{C}}$$ is associated to identity morphism of the corresponding object $$F(X) \in \text{Ob}_{\mathcal{D}}$$

$$F(1_{X})=1_{F(X)}$$
+ morphism association is distributive over composition operator

$$ F(g\circ f)=F(g)\circ F(f)$$

### Contravariant Functor
**Contravariant functor** is almost same as Covariant Functor excecpt that it's not. The object association is same as for Covariant functor. But morphism association happens in a twisted manner. Each morphism $$f \in \text{Mor}_{\mathcal{C}}(X,Y)$$ is associated to $$F(f) \in \text{Mor}_{\mathcal{D}}(F(Y),F(X))$$ (notice the change).
This results in a change in the second property:

$$ F(g\circ f)=F(f)\circ F(g)$$

## Opposite Category
There is darkness and light, good and evil, life and death, beginning and end. And then there is Category and Opposite Category

For each Category $$\mathcal{C}$$ there exists an **Opposite Category** $$\mathcal{C}^{\text{op}}$$. The opposite category has the same objects as the original category, i.e. $$\mathcal{C}^{\text{op}}=\mathcal{C}$$, except that $$\text{Mor}_{\mathcal{C}^{\text{op}}}(A,B)=\text{Mor}_{\mathcal{C}}(B,A)$$, and the composition operator rule is $$f \circ^{\text{op}} g = g\circ f$$. With this definition, a contravariant functor from categories $$\mathcal{C}$$ to $$\mathcal{D}$$ can be defined as functors from $$\mathcal{C}^{\text{op}}$$ to $$\mathcal{D}$$ or from $$\mathcal{C}$$ to $$\mathcal{D}^{\text{op}}$$.

## Natural Transformation
A **natural transformation** $$\Phi$$ acts on two functors $$F$$ and $$G$$ operating between two categories $$\mathcal{C}$$ and $$\mathcal{D}$$ and it associates for each $$X \in \text{Ob}_{\mathcal{C}}$$ a morphism $$\Phi_{X} \in \text{Mor}_{\mathcal{D}}(F(X),G(X))$$ so that for any morphism $$f \in \text{Mor}_{\mathcal{C}}(X,Y)$$, the following diagram is *commutative*.

![]({{site.baseurl}}/images/math/category-theory/natural_transformation.png "Commutative Diagram for Natural Transformation")

A **natural isomorphism** is a natural transformation where $$\Phi_{X}$$ is an isomorphism for all $$X \in \text{Ob}_{\mathcal{C}}$$.

So, isormophisms just mean the way they sound - two entities are isomporhic if they are identical; they behave the same way. So if there exists a natural isomorphism between two functors then they are both essentially *the same*.


[^1]:Also known as **maps** or **arrows**