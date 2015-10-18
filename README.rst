Main Ports Tree of the Hardpan Open Source Port Repositories (GitHub)
=====================================================================
Repository: ``git@github.com:hpan-ports/tree-main``
---------------------------------------------------------------------

This repository comprises a prototype *ports tree* structure,
developed towards a component-oriented methodology for managing of
*port* and *distfile* source components on a FreeBSD operating
system.

In this methdology, each *port* is assigned to an individual Git
source code repository, with each repository thus representing a
singular *port source code* respository. Each *port source code*
repository is then constructed with a *Git submodule*, such that the
*submodule* comprises a reference to the source code repository of
which the containing port's *distfile* is constructed, as would be
referenced to an exact changeset of the respective *distfile source
tree*, within the respective *submodule* reference.

This method serves to ensure that an obvious *version alignment* may
be maintained between *port* and *distfile* components. The *version
alignment* is maintained essentially by way of *submodules* within the
structure of a *ports source tree*.

Secondly,  this methodology allows for *port  updates* to be developed
at a finer granularity than of *the entire ports tree*. Presently, if
in order to update a single *port*, in FreeBSD, the entire *ports
tree* must retrieved -- whether retrieved by way of Subversion, Git,
Portsnap, Curl, or other ports tree retrieval method. With each *port*
being maintained, instead, in a seperate *port source code*
repository, then only a single *port source code* repository would
need to be  retrieved, if as to update the source code of a single
*port*.

Thirdly, this methodology allows for a finer granularity in *issue
tracking*. With an individual *port source code* repository being
defined for each individual *port*, then any issues reported about any
single  *port* may be assigned specifically to the *port source tree*
containing the source code representing the *port* or *package* about
which the individual issue has been reported

Integration with Other SCCM Tools
---------------------------------

With the methdology proposed in this repository, all *port source
code* repositories and all *distfile source code* repositories must be
available via a Git interface. For ensuring consistency of version
control methods onto the complete *ports tree*, any repositories that
may be available in any format as may be mirrored in a Git repository
-- such as with repositories implementing the Concurrent Versions
System (CVS) or the Subversion (SVN) repository format -- these may be
mirroed with the respective Git repository mirroring tool, then
referenced within the singular *ports tree*

The methodology proposed in this repository is applied onto the Git
Software Change and Configuration Management (SCCM) tool. This
methodology may be extended for application with any SCCM tool that
would implement a structure analogous to the Git *submodule*
structure -- such as with regards to the SVN *externals*
structure. Both Git *submodules* and SVN *externals* may be applied 
as structures internal to a single changes repository.

Alternate Tooling: The git-repo tool
------------------------------------

The methodology presented in this repository may also be incorporated
with any single SCCM tool that may be applied in a manner functionally
external to a single changes repository, such as git-repo_, a tool
applied in both the `Google Chromium<https://www.chromium.org/>`_ and
`Android Open  Source<https://source.android.com/>`_ Projects. The
git-repo_ tool effectively serves as to *collate* individual *project*
objects on a basis of a references to individual project source
repositories, with such references being maintained in a single
*manifest* file for the git-repo_ tool. The *manifest* file
furthermore serves to allow for topical *grouping* of *project*
objects, in a manner such as may be integrated with a system for
*release management*. In application for *release engineering*,
git-repo_ ensures a consistency across *branch* and *version* tags
from referenced projects.

.._git-repo: https://code.google.com/p/git-repo/

Describing Port Development Projects and Repsosities in RDF Format
------------------------------------------------------------------

The *ports* model developed of this repository may be furthermore
extended with a *project metadata* format, such as defined in the
`Description of a Project (DOAP)<https://github.com/edumbill/doap/wiki>`
RDF schema. The DOAP RDF schema may be applied as an alternative 
to the *plain text* project description format presently applied in
FreeBSD port descriptions. In an application of the DOAP RDF schema, a
metadata management tool may be developed such that may serve as to
record information about port maintainerhip, port description, port
upstream homepage, port issue tracker page, and port repository
location, in an applciation of the Resource Description Framework
(RDF) XML format, and as extending of the DOAP RDF Schema.

In adopting the *distfile submodule* model proposed in this prototype 
repository, the DOAP RDF schema may be furthermore extended as for a
purpose of denoting a port's exact *distfile source code* repository,
in the project's DOAP description file. Such an annotation may serve
as an *informative  reference*, if available in parllel to a port's
*distfile submodule* or as a *primary reference* if the port's
*distfile source code* may not be available in a Git repsository
format.

Moreover, the DOAP description format may be extended as to provide
any informative references towards an extended *issue tracking* in
integration with any number of *upstream development projects* of
which any single *port* may be derived -- such that may serve
to aid any later port maintainers, in regards to *issue tracking*.

For a purpose of denoting an SCCM repository in a DOAP description
file, a platform-agnostic repository URI syntax may be applied -- such
as of the URI syntaxes developed in the `Maven SCM<https://maven.apache.org/scm/>`
plugin -- as illustrated `per application<https://maven.apache.org/scm/scms-overview.html>`,
in the documentation for `Maven SCM<https://maven.apache.org/scm/>`.
