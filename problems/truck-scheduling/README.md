<!--
SPDX-FileCopyrightText: 2024 Samuel Carinhas <samuelsantos.c.2001@gmail.com>

SPDX-License-Identifier: CC-BY-4.0
-->

# Problem Name – Truck Scheduling

Samuel Carinhas, University of Coimbra, Department of Informatics Engineering  

<!-- Put two empty spaces at the end of each author line except the last for
proper formatting -->

Copyright 2024 Samuel Carinhas.

This document is licensed under XXXX.

<!-- Complete the above accordingly. Copyright and licensing information must be
consistent with the comment at the beggining of the markdown file -->

## Introduction

One issue reported by the Port of Sines is the substantial number of truck trips without cargo, referred to as empty trips, due to the lack of optimization. This problem aims to optimize the scheduling of cargo transport from the Port of Sines to any destination, and vice versa, with the goal of minimizing the kilometers traveled by trucks without cargo.

## Task

Given a list of trucks, their availability, and the cargo to be transported, along with a distance matrix, schedule each cargo with a truck and a time slot. The objective is to minimize the number of kilometers traveled by trucks without cargo and to maximize the number of scheduled cargo deliveries.

## Detailed description

### Important Definitions:

#### Truck

A truck is characterized by an ID plate, a list of available time slots, and a list of supported cargo types.

#### Timeslot

A time slot is defined by a start date and an end date, indicating when the truck becomes available and when its availability ends. Additionally, it specifies the truck's coordinates at the start of the slot, as well as the location where the truck must be at the end of the slot.

#### Cargo

A cargo is characterized by its type, the date it becomes available for delivery, and the delivery deadline.

### Problem statement

Let $t_n$ be the number of cargos assigned to time slot $t$. $t_{source}$​ and $t_{target}$ represent the starting and ending positions of the time slot, respectively, and $t_{c_i}$ denotes the location of the $i^{th}$ cargo within the slot.

**Objective function:** $\min \sum_{ t \in T_S } {d(t_{source}, t_{c_0}) + \sum_{i=1}^{t_n-1} d(t_{c_{i-1}}, t_c) + d(t_{c_{t_n}}, t_{destination})} + \sum_{ t \in T_S} t_n$

### Constraints

* The total travel time needed to deliver the schedule cargos for a specific slot must be less or equal to the slot deadline. $\sum {time(t_{source}, t_{c_0}) + \sum_{i=1}^{t_n-1} time(t_{c_{i-1}}, t_c) + time(t_{c_{t_n}}, t_{destination}) + \sum_{c \in t_c} time(c)} \leq t_{end} ~~\forall t \in T_S$, where $time(c)$ is the total cargo travel time (from cargo source to cargo destination).

* No cargo can be assigned before its availability and every cargo should be delivered before its deadline. $(t_{start} \leq c_{start}) \land (c_{delivery} \leq c_{end}) ~~\forall c \in t_c ~~\forall t \in T_S$, where $t_{start}$ is the starting date for the time slot, $c_{start}$ and $c_{end}$ are the availability and deadline dates for the cargo and $c_{delivery}$ is the scheduled delivery date for the cargo.

* Every cargo type must be supported by the scheduled truck. $c_{type} \in t_{types} ~~\forall c \in t_c ~~\forall t \in T_S$

## Instance data file

Describe the format of a problem instance file.

## Solution file

Describe the format of a solution file.

## Example

### Instance

Provide a small example instance in the described format.

### Solution

Provide a feasible solution to the example instance in the described format
(including its evaluation measure).

### Explanation

Optionally, provide a descriptive and/or visual explanation of the solution (and
its evaluation measure value) for the instance.

## Acknowledgements

This problem statement is based upon work from COST Action Randomised
Optimisation Algorithms Research Network (ROAR-NET), CA22137, is supported by
COST (European Cooperation in Science and Technology).

<!-- Please keep the above acknowledgement. Add any other acknowledgements as
relevant. -->

## References

Put any relevant references here.
