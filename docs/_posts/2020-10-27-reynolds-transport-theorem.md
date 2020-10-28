---
layout: post
title: Reynolds Transport Theorem
---


## Motivation For Post

]The Reynolds Transport Theorem (hereafter referred to as RTT), for me, was the most fundamental element of beginning to understand fluid mechanics. This may be obvious to some; however, for me it was just this hand wavy cool math trick used to derive conservation laws until I finally conceptualized it. Here is my take on it!

## Why do we need RTT?

RTT is an incredibly important derivation for understanding fluid mechanics. The reason for this begins with the difference between taking an **Eulerian** or **Lagrangian** approach to describing the system that we are interested in. A Lagrangian approach, put simply, is when you consider the perspective of an element wherever it may be in time, space. In that sense, we are following a fluid particle as it moves. An Eulerian approach is one in which we sit back at some fixed position and define some quantity everywhere. Intuitively, a Lagrangian approach makes much more sense, after all we are far more use to it than an Eulerian approach. We think in Lagrangian terms all the time. When we consider physics in high school and contemplate a free body diagram on a static object, like a block, this is Lagrangian, albeit a simple example since the object is still. If we consider the forces on a rocket as it is propelled into space naturally we think about the physics from the perspective of the rocket as it moves. This is also Lagrangian. The Eulerian perspective, while mathematically simple, is the far more confusing idea in my opinion.

So why do we need to consider these two perspectives when we think about fluid mechanics? We need to consider the Lagrangian perspective because it is far easier to apply physics from this POV. We consider what a fluid element feels and track that from the POV of the particle instead of continuously redefining the physics acting on a particle in terms of some fixed point (that sounds awful!).

On the other hand, measuring characteristics of fluid flow from a Lagrangian perspective can prove to be a nightmare. If we want to know the velocity of a fluid it is far more easy to install measurement devices at fixed points and define the velocity field of the flow this way, from a fixed perspetive using the Eulerian approach.

The issue we run into in fluid mechanics is interweaving these ideas so that we can optimally assess the evolution of a fluid element in both time and space.

## Some Terminology

When we think about a fluid there are two more very important terms: **Control Mass** (CM) and **Control Volume** (CV). The CM encapsulates the Lagrangian approach. It is some mass or element that we choose to follow in the situation of interest. Alternatively, the CV encapsulates the Eulerian approach. It is some volume that we hold constant in space, in some sense it is this imaginary measurement device that we use to mathematically consider **the change of some quantity over time** and ultimately perform **accounting** on it.

It is also helpful to understand two quantity types: **Extensive** and **Intensive**. An extensive quantity (N) is the amount of some transportable quantity like momentum, a contaminant, vorticity, etc in the CM. In contrast, an intensive quantity is the **per unit mass** ($$\eta$$) version of the extensive quantity. Naturally, we track the extensive quantity using the Lagrangian approach as it characterizes the fluid element we are considering, and we account for the intensive quantity using the Eulerian approach.

## Supporting Mathematics

Consider a control mass with some quantity **N** traveling through a fixed control volume set in space. Here we note that the control mass is some amount of mass that we are following, and tracking as it goes through the fixed space (the CV) that we have defined. Simply put, we want to account do some accounting on the CM from the perspective of the CV. In this way our consideration of the CV is an **accounting** task not unlike tracking how much money you have in your bank account, while the consideration of the CM is a physical reprsentation of the same change. Therefore, in general we can say that the quantity **N** is changing due to some physical laws and characterize its change in time with **term 1**:

$$ \frac{dN}{dt} \Big|_{CM} $$

We are now done for the moment thinking about the Lagrangian perspective since we have now used it to define the physics of this equality we are trying to formulate. Now we must try to desribe how we can **measure & account** for this using an Eulerian approach. By considering the fixed CV in space and some logic we can realize that we need to track two things: the **accumulation** of our quantity **N** in the CV over time and the net flux of **N** out of the CV. In other words, if we sum all of the fluid/quantity N going in and out of the CV, how much total is leaving? If this flux quantity is negative then the CV is seeing quantity come into it; however, if the opposite is true then overall it is seeing the quantity leave it.

Now we must simply translate these ideas to math!

To explain this we will consider this from the perspective of a bank account. My CM term that I described above would be equivalent to earning/spending your money. It is the physical explanation for the change in money that you have over time. The **accounting** we are about to do is almost perfectly described by the accounting we would do on our bank accounts.

First, lets consider the idea of **accumulation**. We want to know how much of **N** is accumulating in the CV (that can be negative or positive). As the case is with money, our bank account can grow or shrink as a result of what is physically happening. Since we are accounting for some quantity in a CV we need $$\eta$$ to be a per mass value so that if we multiply by fluid density $$\rho$$ we get **N per volume**. If we want to total value of N in the CV then we can simply sum it with integration! This yields **term 2**:

$$\int _{CV} \rho \eta dV$$ 

**Term 2** defines the amount of **N** in the CV; however, we said we want to know about accumulation which has a time component. Thinking about the bank account again, **Term 2** as it stands would just tell us whats in our bank account without regard for time. We want to characterize this in terms of time though, so we will differentiate **Term 2** with respect to time to get a more descriptive and final form of **Term 2** as:

$$\frac{d}{dt} \int _{CV} \rho \eta dV$$ 

Finally, we need to account for the net flux in the CV. If I were to measure this quantity for my bank account, I would never need to know what is in my bank account, just what is coming in and leaving. Therefore, I would just need to find a way to measure what is coming in and out of the surfaces of the CV in the more general case we are considering. For an infinitesimal area I want to know how much of the quantity **N per unit volume** is leaving/entering that small area. Simply put, this is the volumetric flowrate through that small area, which discretely written is $$U*A$$ (velocity times area) with units of $$ \frac{length^3}{time}$$. If we multiply this value by the **N per volume** which we know is $$\rho \eta$$ we get the flux of N out of that small area:

$$ \rho \eta UA $$

Because we want to generalize this idea to reflect a three-dimensional CV where the flux can come through an infinite number of small areas (that we want to find the sum of) with varying directions (in/out) we will rewrite this idea in terms of a standard surface integral to obtain **Term 3**:

$$\int_{CV} \rho \eta (\vec{u} \boldsymbol{\cdot} \vec{dA}) $$


## The Reynolds Transport Theorem!

We made it! The final form of the Reynolds Transport Theorem is as follows:

$$ \frac{dN}{dt} \Big|_{CM} = \frac{d}{dt} \int _{CV} \rho \eta dV + \int_{CV} \rho \eta (\vec{u} \boldsymbol{\cdot} \vec{dA}) $$

where **N** is a transportable quantity and $$\eta$$ is equal to $$\frac{N}{mass}$$.

![figure1](/assets/img/RTT_CV.png){: height="400px" : border="1px"}

**Figure 1:** *Representation of CV and CM.*

### References:

This is an unofficial reference. Everything I discuss here was learned through reading **Fluid Mechanics** *by Kundu* or through my Stanford courses: taught by *Dr. Nick Oullette (CEE 262A)* and *Dr. Ali Mani (ME 351A)*. 






