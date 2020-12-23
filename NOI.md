# Improving the Foundations and Maintenance of Matplotlib and CartoPy

Matplotlib is an established open source plotting library with a
BSD-derived license that is currently used through out both the SMD
science community and the wider scientific community for both
publication quality figures and for interactive data exploration.  The
initial commits in our version history date to early 2003 and the
initial work was done in 2001-2002. Over the last 17 years the project
has grown to have over 1,000 individual contributors, over a million
users, and is in the top 100 most downloaded Python packages. We are a
dependency of many down-stream libraries, including yt, astropy,
ArviZ, and xarray. CartoPy is a Matplotlib extension library that
brings support for mapping applications to Matplotlib, providing
support for plotting using a variety of map projections (both
terrestrial and non) as well as providing out-of-the-box support for
many terrestrial map features. CartoPy is currently the only
Matplotlib-based plotting library for mapping applications being
actively developed in the Python ecosystem. CartoPy is frequently used
for earth science applications, including many uses of NASA Earth
science datasets.

Matplotlib supports plotting unit-aware data structures which have
been used to support spaceflight operations by Monte, JPL's mission
design and navigation software system. Initial development of this
capability was supported by NASA. However, this support is under
documented making it difficult for users to understand how to fully
make use of the capability. Further, because we do not have full test
coverage of all plotting functions to verify that they correctly
handle units we have had a number of regressions in the
functionality. We will propose to write thorough user and technical
guides to working with unit-aware data in Matplotlib, add 100% test
coverage of unit support in our plotting routines, and fix any issues
and inconsistencies discovered in this process.

CartoPy's mapping capabilities leverages the widely-used PROJ library
for mapping projections and the GEOS library for geometry
applications. Currently, CartoPy maintains custom code to interface
Python with these C-based libraries. As part of this work, we propose
porting Cartopy to instead use existing libraries that provide Python
bindings for these libraries, PyPROJ and PyGEOS. Not only will this
reduce CartoPy's overall amount of code and enhance maintainability,
but it will also address two of the biggest challenges that occur in
packaging CartoPy for its user-base.

Matplotlib and Cartopy are community-driven projects, but we have
grown to the point where we need developers with the time to organize,
plan, and make decisions. Issues and Pull Requests (PRs) are submitted
faster than our volunteers can review them;Matplotlib has accumulated
about 1300 open Issues and 300 open PRs due to this imbalance, while
CartoPy currently stands at 229 open issues and 40 open PRs. There may
be critical bug reports or insightful feature requests among the
former, while among the latter are useful contributions or bug fixes
that would improve the libraries for direct users and downstream
packages. The backlog is discouraging for new and occasional
contributors and distracting for core developers. The resources we
will request will help to significantly reduce, but not eliminate,
this backlog.
