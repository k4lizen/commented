# Commented source files

I believe that while reading a new codebase it can be very useful to add clarifying comments to it yourself.
For C code, I recommend prefixing them with `//!` to differentiate them from normal comments.

For reproducability, pick the latest stable version of the software you are looking at, and create a new branch `the_stable_version-commented`. After you are done, commit your changes. Ideally you would like to save these comments somewhere, but keeping all the repos you comment on around is annoying, so create a patch file and add it to this folder.

Create a patch with:
```bash
git format-patch -1 HEAD
```
Where `-1` denotes how many commits are included in the patch.

The structure of this folder is the following:
+ repo_name-tag-explored_system
    + touched_source_file_1.c 
    + touched_source_file_2.c 
    + touched_source_file_3.c 
    + 0001-explored_system-comments.patch 
    + notes.txt

The notes.txt file should have at least this type of info:
```
My kfree() investigation.

Comment base:
	https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
	6a753907865e35ae986b7b2ad48daa1eab4bcf3a
	v6.19.6

Comment commit:
	efa63bfeef1aa9a599df0d1ed69e1615503dbb17
```

I currently don't have a solution for comments that I want to keep private to myself for some time. (A `private/` folder would not be synced between devices.) Maybe just a separate `commented-private` private github repository? Well, we get there when we get there.
