## Forker's note: This branch makes `chrt`, `renice`, `ionice`, and `taskset` setuid root

for the convenience of users who aren't concerned about denial-of-service threats.

It drops privileges before actually exec'ing.


				  util-linux

		util-linux is a random collection of Linux utilities

     Note: for the years 2006-2010 this project was named "util-linux-ng".

MAILING LIST:

      E-MAIL:  util-linux@vger.kernel.org
      URL:     http://vger.kernel.org/vger-lists.html#util-linux
      ARCHIVE: https://lore.kernel.org/util-linux/

      The mailing list will reject email messages that contain:
       - more than 100K characters
       - html
       - spam phrases/keywords
      See: http://vger.kernel.org/majordomo-info.html#taboo

IRC CHANNEL:

      #util-linux at freenode.net:

      irc://chat.freenode.net/util-linux

      The IRC channel and Mailing list are for developers and project
      maintainers. For end users it is recommended to utilize the
      distribution's support system.

BUG REPORTING:

      E-MAIL: util-linux@vger.kernel.org
      Web:    https://github.com/karelzak/util-linux/issues

      This project has no resources to provide support for distribution specific
      issues. For end users it is recommended to utilize the distribution's
      support system.

NLS (PO TRANSLATIONS):

      PO files are maintained by:
	  http://translationproject.org/domain/util-linux.html

VERSION SCHEMA:

      Standard releases:
	  <major>.<minor>[.<maint>]
	     major = fatal and deep changes
	     minor = typical release with new features
	     maint = maintenance releases; bug fixes only

      Development releases:
	 <major>.<minor>-rc<N>

SOURCE CODE:

 Download archive:
	  https://www.kernel.org/pub/linux/utils/util-linux/

 SCM (Source Code Management) Repository:

    Primary repository:
	  git clone git://git.kernel.org/pub/scm/utils/util-linux/util-linux.git

    Backup repository:
	  git clone git://github.com/karelzak/util-linux.git

    Web interfaces:
	  http://git.kernel.org/cgit/utils/util-linux/util-linux.git
	  https://github.com/karelzak/util-linux

      Note: the GitHub repository may contain temporary development branches too.

      The kernel.org repository contains master (current development) and stable/*
      (maintenance) branches only. All master or stable/* changes are always pushed
      to both repositories at the same time.

    Repository Branches: 'git branch -a'
	  master branch
	   - current development
	   - the source for stable releases when deemed ready.
	   - day-to-day status is: 'it works for me'. This means that its
	     normal state is useful but not well tested.
	   - long-term development or invasive changes in active development are
	     forked into separate 'topic' branches from the tip of 'master'.

	  stable/ branches
	   - public releases
	   - branch name: stable/v<major>.<minor>.
	   - created from the 'master' branch after two or more release
	     candidates and the final public release. This means that the stable
	     releases are committed, tagged, and reachable in 'master'.
	   - these branches then become forked development branches. This means
	     that any changes made to them diverge from the 'master' branch.
	   - maintenance releases are part of, and belong to, their respective
	     stable branch. As such, they are tags(<major>.<minor>.<maint>) and
	     not branches of their own. They are not part of, visible in, or
	     have anything to do with the 'master' development branch. In git
	     terminology: maintenance releases are not reachable from 'master'.
	   - when initially cloned (as with the 'git clone' command given above)
	     these branches are created as 'remote tracking branches' and are
	     only visible by using the -a or -r options to 'git branch'. To
	     create a local branch use the desired tag with this command:
	     'git checkout -b v2.29.2 v2.29.2'

    Tags: 'git tag'
	   - a new tag object is created for every release.
	   - tag name: v<version>.
	   - all tags are signed by the maintainer's PGP key.

    Known Bugs:
	- don't use tag v2.13.1 (created and published by mistake),
	  use v2.13.1-REAL instead.

WORKFLOW EXAMPLE:

 1) development (branch: <master>)

 2) master release (tags: v2.29-rc1, v2.29-rc2, v2.29, branch: <master>)

 3) development (work on v2.30, branch: <master>)

 4) fork -- create a new branch <stable/v2.29> based on tag v2.29

     4a) new patches or cherry-pick patches from <master> (branch: <stable/v2.29>)

     4b) stable release (tag: v2.29.1, branch: <stable/v2.29>)

     4c) more patches; another release (tag: v2.29.2, branch: <stable/v2.29>)

 5) master release v2.30 (branch: <master>)
    ...

where 3) and 4) happen simultaneously.

