**Review 1**

Review of: One-dimensional turbulence (ODT): computationally efficient
modeling and simulation of turbulent flows

This paper presents an easy to use software for the One-dimensional
Turbulence (ODT) model that helps to remove the barrier for researchers
wanting to learn about ODT. The code is easy to understand and change to
suit different requirements. The paper is well-written, the software is
carefully explained, and the example provided demonstrates the use of
the software. I recommend publication subject to some minor edits and
clarifications as noted below.

-   Building OPT:

    -   YAML: specify the name of the needed yaml package is: yaml-cpp

-   Input files: Consider adding a feature that helps to specify the
    dumpTimes. For example, add the capability to parse the following
    values (Start, End, Step ) from the input file rather than
    specifying all the times you want to save the data manually.

-   Running ODT:

    -   The running interface is not trivial and limits the user to a
        predefined data storage location.This may cause problems for
        some users.

    -   My recommendation is to put all these run scripts under a single
        python interface that will allow the user to select the number
        of realization, the number of processes ( when running in
        parallel ), the input file, \... .

        -   consider using python classes for the interface, it will
            make you code much cleaner

        -   check argparse module in python!

-   Data files and Post-processing:

    -   In the paper, you mentioned in line 118 that \<200b\>the package
        contains auxiliary data processing and visualization tools.
        However, later in section 2.3.4 Data files and post-processing
        you mentioned in line 237 that those tools are organized by case
        type meaning that these post-processing tools are specific for
        the input files provided as examples. This may cause confusion
        to the user.

    -   Also, you didn't mention the tools you provided that help the
        user load the data. (ODT/Post/tools)

        -   I recommend that you put these functions under a python
            class that takes as a value the path to the data you saved.
            This will give flexibility to the user to load any data
            stored on his local or remote machines.

        -   Describe those functions in the paper.

    -   Also, I would recommend that the post-processing data examples
        you provided be written in Jupyter notebooks for clarity.

-   Impact:

    -   In the impact section line 298 the reference is missing.

-   Lines 78 and 79: very cumbersome sentence. Suggest you use: the
    first term on the RHS of eq. 1 is\... while the second term is\...

**Review 2**

Reviewer \#2: The paper describes an open-source code for simulating
one-dimensional turbulence (ODT).

As highlighted from the Authors in the impact Section, implementing ODT
is not an easy task hindering the spreading and use of this useful
model. The present open-source tool will be a first step to increase the
popularity of the technique among the scientific community in multiphase
and reactive flows.

The code is easy to read, to eventually modify and to use. The
documentation and the provided examples are clear and exhaustive.

The Reviewer has a personal curiosity on the technique (outside the
scope of the Journal). ODT has been used in combination with Lagrangian
particle models. We know those ( heavy ) particles tend to stay away
from the vortical regions, but if we are in 1-D, what is vorticity?
Should we look to other \"equivalent\" observables?

Minor, a reference appears as \[? \] on page 12.
