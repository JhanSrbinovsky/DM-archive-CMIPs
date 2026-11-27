# archive-CMIP6

This archive-CMIP6 branch of the repository contains the directory tree structure that follows from that existing on `/g/data/archive/CMIP6/`. Note - this tree structure does not include any of the experiment data. It does contain however instances of `Notes.md` throughout, which describe the immediately visible experiments on each path. This information includes their status/location on each file system.

Broadly speaking the file systems which use this tree structure are:

1. The "hard" copy on `/g/data/archive/CMIP6/`. This is the raw model data as output per experiment.
2. The tape back up in the `datastore/` on petrichor@CSIRO.

For convenience we also have tape back ups on mdss@NCI, and **temporary** backups of the "hard" data at `/scratch/p66/gdata_p73_hold/`.

A git working copy of this tree and Notes is maintained on `/g/data/archive/CMIP6/` and `scratch/`. A manually maintained copy (See below) of the same structure exists on the datastore and mdss systems. 

## Manually maintained copy

Ideally for data management purposes the tree structure across platforms should be the same. However, introducing a git repository to the datastore is not advisable as git operations would continually change files, messing with the archival system. Implementation on mdss would have additional problems.  

The manually maintained copies contain information corresponding to the git commit which it represents (See code below). Although, it is likely that the only update to the git version or for that matter the tape back up version is likely to be to the `Notes.md` files.





```
{
  echo "commit:  $(git rev-parse HEAD)"
  echo "branch:  $(git rev-parse --abbrev-ref HEAD)"
  echo "describe: $(git describe --always --dirty --tags)"
  echo "date:    $(git log -1 --format=%cd --date=iso)"
  echo "author:  $(git log -1 --format='%an <%ae>')"
  echo "subject: $(git log -1 --format=%s)"
  echo "remote:  $(git remote get-url origin)"
  echo "status:"; git status --short
} > git_info.txt
```

