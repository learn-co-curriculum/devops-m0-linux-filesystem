# The Linux Filesystem

## Learning Goals

- Learn what a filesystem is and how it is structured
- Gain understanding of how the Linux filesystem works
  - Root directory and its child folders
  - "Everything is a file"
- Difference between binary and text files

## Introduction

An operating system's **filesystem** is the way it organizes and stores files on a computer. It provides a hierarchical structure that allows files to be organized in a logical manner, making it easy to find and access.

As you probably already know, a **directory**, also known as a **folder**, are what we use to organize files and other directories on a computer. They are esentially containers that hold other files and directories.

The *Linux* filesystem is the hierarchy of directories and files that is used to organize and store data on a *Linux* system. At the top of the filesystem is the *root directory*, represented by a single forward slash (/). This directory is the parent of all other directories and files on the system, and it serves as the starting point for all pathnames.

## The root directory

The root directory contains several other directories, each of which serves a specific purpose. Here's an example of what the root directory looks like on most *Linux* installations out of the box:

![Root directory](https://curriculum-content.s3.amazonaws.com/6685/devops-m0-linux-filesystem/root-directory.png)

Here's a summary of what each folder represents:

- `/bin`: Contains binary executables, or programs, that are used to perform various tasks on the system. For example, the `ls` command, which is used to list the contents of a directory.
- `/boot`: Contains files that are needed to boot the system, such as the bootloader.
- `/dev`: Contains special files that represent devices on the system, such as hard drives, keyboards, printers.
- `/etc`: Contains system-wide configuration files, such as settings for network interfaces and services.
- `/home`: This directory is where users' personal files and directories are stored. Often used to store documents, music, and other files that are specific to each user.
- `/lib`: Contains shared libraries, which are collections of code that can be used by multiple programs on the system.
- `/mnt`: Often used as a mount point for attaching additional storage devices, such as external hard drives, to the filesystem.
- `/opt`: Often used to store optional software packages that are not part of the core system.
- `/root`: This directory is the home directory for the root user, which is the administrative user on a Linux system.
- `/usr`: Contains user-related programs and data, such as applications, libraries, and documentation.
- `/var`: This directory is used to store files that are expected to change frequently, such as logs and temporary files.

We'll go over users and permissions in the next module, but for now, understand that most of these folders are *read-only* by users other than the *root* user. So if you try creating a file in your virtual machine in one of these directories, you will most likely be unable to. A notable exception is the `/home` directory; each user has their own directory, and full *read-write* access over it (e.g. `/home/thomas`).

## Everything is a file??

You might find it surprising that in *Linux*, there is a phrase that "everything is a file". This refers to the fact that from the perspective of the operating system, pretty much all forms of data are treated as files. This includes not only traditional files that contain text or other data, but also directories, devices, connections, etc.

So how does this work? In *Linux*, data is represented by **inodes**, which are a type of data structure that contain information about the file. This information includes its size, permissions, location, id, etc.

The reason this is important will become more apparent later, but in essence, having everything be a file means that different types of data can be easily combined and manipulated together. You can use the same techniques and tools as regular files for things like network connections.

## Binary vs Text files

Generally, a file can take one of two forms: a *Binary* or *Text* file. 

**Text files**, as the name implies, are files that contain human-readable characters and are (generally) used to store text or other human-readable data. They are limited to storing text data, as they are represented using the *ASCII* or *Unicode* character sets, which can only represent text.

> **Aside:** *ASCII* and *Unicode* character sets are what computers generally use to represent characters in digital form. They are sets of codes that can represent letters, numbers, punctuation, and all sorts of characters. **ASCII** is a very small character set and only includes characters used in the English language; **Unicode**, on the other hand, is a much larger character set that includes characters from many different languages and scripts.

**Binary files**, conversely, are those that contain *binary data*, which is data represented in machine-code using the *binary* language, consisting of 0s and 1s. These types of files are are capable of storing any type of data, including text, numbers, images, audio, video, games, etc. 

Binary files are used for storing data that is used by computers, such as programs and system files, whereas text files are typically used for documents, source code, and other types of human-readable data.

If you want an easy way of knowing whether a file is a text or binary file, you can simply try opening it with a text editor. If it looks like a jarbled mess, it's probably a binary file.

![Binary vs Text files](https://curriculum-content.s3.amazonaws.com/6685/devops-m0-linux-filesystem/binary-vs-text.png)

## File extensions

A **file extension** is a set of characters added at the end of a file name, used to determine what program should be used to open the file. These are typically three or four characters long and mostly consist of letters (and sometimes numbers).

For example, `file.txt` has the `.txt` extension, indicating it is a text file and can be opened by any program that can interpret text. `song.mp3` is an audio file, `.jpg` is an image file, etc.

These extensions help the operating system and other programs decide how to handle the file. It's important to note that the extensions by themselves don't do anything, they're purely to tell the operating system what to use to open them. For example, if you get a `.txt` file and rename it to `.mp3`, it'll be opened by a music player (even though it won't be able to play it). If you rename it back, it'll work just fine. You'll see text files called all sorts of things (`.ini`, `.cfg`, `.txt`, `.py`, etc.) but they can all be opened by text programs.

## Conclusion

The *Linux* filesystem (as with most file systems) is organized in a hierarchical manner, with directories containing other directories and files. This allows for a logical and intuitive organization of data, and it makes it easy to find and access the files you need. It also provides a level of security, as the filesystem permissions system can be used to control which users and programs have access to which files and directories.

Overall, the *Linux* filesystem is a core part of the system, and it is important for anyone using a *Linux* system to have a basic understanding of how it works and how to navigate it. With practice, you will become more comfortable with the filesystem and be able to use it effectively to manage and access your data.
