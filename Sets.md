# Sets
Sets are a fundamental concept from [[Mathematics]].
This is an informal intro to set theory (see [[Axiomatic vs informal set theory]])


## Some definitions:

A set $A$ is/has ...
- **open** if the metric of all points with some center point is "$\leq\epsilon$" 
- **closed** if its complement is open
- **closure**: union of set with boundary, denoted as $\bar A$
- **dense** in a larger space $X$, if either
	- the closure of $A$ is $X$
	- every point in $X$ either belongs to $A$ or is a limit point of $A$
- **bounded**: ball with finite radius encloses the set
- **complete**: all Cauchy sequences converge in $A$
- **completion**: union of set with all limit points of cauchy sequences of set
- **compact**: 
	- bounded and complete; 
	- each sequence has convergent subsequences; 
	- $\implies$ complete
- **connected**: connection between any two points in the set
- **simply connected**: without holes, or rather connected and every closed path is "contractible" to a point in the set (which is a topological term)

#TODO: how does denseness and completeness relate?


## Source
- Prof. Auzinger - Analysis 2 für TPH, TU Wien lecture notes
- Analysis II für Physiker, Universität Wien lecture notes
- Multiple wikipedia articles
