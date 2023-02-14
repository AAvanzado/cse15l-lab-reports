# Lab Report 3

# Researching the `find` Command

## `-mtime` Option
Example 1
```
find written_2 -ctime 0
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRHawaii.txt
```
Here it is finding files within `written_2` whose status has been changed in the last n 24 hour periods which in this case since n = 0, the files outputted have been changed in the last 24 hours. This is useful for keeping track of recently changed files in case you changed multiple files and forgot which ones you actually updated.

Example 2
```
find written_2 -ctime -7
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/IntroJapan.txt
```
This time n = -7 which indicates files changed in the *last* 7 days (a +7 would indicate changed files *more than* 7 days ago). This is useful if you have worked across multiple files over the past week and want to keep track of which files you have changed.

[Source Used](https://man7.org/linux/man-pages/man1/find.1.html#top_of_page)

## `-empty` Option
Example 1
```
find written_2 -empty
```
Here the `-empty` option checks within a directory if there are any empty files or empty directories and as the `written_2` currently is, there are no empty files or directories and therefore, there is no output. This is useful to make sure that there are no empty files or directories that are currently inside your directory.

Example 2
```
find written_2 -empty
written_2/non-fiction/OUP/TestEmptyDirectory
written_2/travel_guides/berlitz2/TestEmptyFile.txt
```
After creating an empty directory and and empty txt file, they now both appear when running the `-empty` option. Here we can see that this option is handy when combined with find because we can see the path to the empty directories/files so that we can easily locate them to be removed if need be.

[Source Used](https://man7.org/linux/man-pages/man1/find.1.html#top_of_page)

## `-type` Option
Example 1
```
find written_2 -type d
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```
This `-type` option basically filters the results based on the provided "type", which in this case it is `-type d` and "d" stands for directory. Thus, only the directories are outputted which is useful for when you want to use the find command and only want to look at the directories.

Example 2
```
find written_2 -type f
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
...
(continues on to output all the files under written_2)
```
In this example, instead of `-type d` which filtered the result by directory, `-type f` filters the result by outputting only the files. This would be useful in determining all the files within a directory without having to look at all the different subdirectories.

[Source Used](https://man7.org/linux/man-pages/man1/find.1.html#top_of_page)

## `-size` Option
Example 1
```
find written_2 -type f -size -1k
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
```
Here, `-size -1k` is finding the files (thanks to the `-type f`) that have a file size of *less* than 1 kilobyte. This would be useful in determining which files are taking up the least amount of space.

Example 2
```
find written_2 -type f -size +200k
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/Canada-WhereToGo.txt
```
In this example, we are finding files that have a file size of *more* than 200 kilobytes. This functionality is useful in determining which files are taking up the most space within a given directory.

[Source Used](https://man7.org/linux/man-pages/man1/find.1.html#top_of_page)
