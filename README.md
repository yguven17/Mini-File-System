# project3COMP 304 Project 3
Yakup Enes GÜVEN

Disk Manipulation
1. mini fat create(filename, block size, block count) creates a new virtual disk
and stores it inside the filename.
I  created virtual disk file which is exactly block count*block size bytes and
reside in project directory immediately after creation.
The function returns a FAT FILESYSTEM object with its fields set properly.
2. mini fat save(fs) which completely saves a filesystem to the real file on the disk.
After the save operation, the virtual filesystem completely stored inside the
single file passed to create and can be loaded later.
3. mini fat load(filename) load a previously saved virtual disk filesystem from
a real file in project directory. The loaded virtual filesystem is identical
to the one that was saved.
4. mini fat dump(fs) which dump the metadata of the virtual filesystem and the
virtual files within it, sans the actual file data.


File System Manipulation
1. mini file dump(fs, file) provides a readable file’s metadata,
including its filename, size, blocks used to store its data, etc.
2. mini file open(fs, filename, is write)  opens a file for reading or writing.

Once a file is opened, a FAT OPEN FILE structure is returned as a file handle that can be
passed to other APIs that work with open files. This structure includes 
whether the file was opened in read or write mode, and what the current cursor position
is inside the opened handle.

3. mini file size(fs, filename)  return the size of a file as an integer (in bytes).
If the file does not exist, returns 0.
4. mini file close(fs, open file)  close an open file handle.
5. mini file delete(fs, filename)  delete a file from the virtual disk. If the file is
already open, it cannot be deleted. Returns true on success.
6. mini file seek(fs, open file, offset, from start)  change the position of
the cursor in an opened file. 
7. mini file write(fs, open file, size, buffer)  write size bytes taken from
buffer to the open file.

8. mini file read(fs, open file, size, buffer)  read size bytes from open file
and put it into buffer.

