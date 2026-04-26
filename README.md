A new inode type T_SYMLINK was introduced. The symlink system call creates a new inode of this type and stores the target path in its data blocks.

The open() system call was modified to resolve symbolic links. When a symbolic link is encountered, the system reads the stored path and continues resolution. Chained links are supported.

A depth limit of 10 is used to prevent infinite loops.

The implementation was tested using testsymlink.c, and all tests passed successfully, including creation, resolution, and loop detection.
