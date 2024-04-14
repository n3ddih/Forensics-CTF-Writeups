# FU Secathon Writeup

2021 - Forensics category - FRS301

## Briefing

The challenge is about hidden file height.

> **For example**: an image has the real height of 500px but it only show 300px when you view it.

The player need to identify which byte in the header contains the value of the height information then change it to the correct value.

**About File Header**:

> File header are usually stored at the start of the file, they can easily be examined by using simple software such as a text editor or a hexadecimal editor.
> 
> File headers may contain metadata about the file and its contents. For example, most image files store information about image format, size, resolution and color space, and optionally authoring information such as who made the image, when and where it was made, what camera model and photographic settings were used (exif data), and so on.
> 
> Source: Wikipedia - File Header

[Dowload file here](https://github.com/n3ddih/FuSec2021_Writeup_FRS/raw/main/FRS301/flag.bmp)

## Details

We know that image metadata can contain information about its size. Next is to identify where is it?

In the [Bitmap file header structure](https://en.wikipedia.org/wiki/BMP_file_format#Bitmap_file_header), we can see that `the common Windows format is the BITMAPINFOHEADER header`, and `the bitmap height in pixels according to the table has offset 16 in hex`.

Upon inspecting the image in HxD, we can *increase the hex value in offset 16 (hex)*, the flag is now visible.

![image](img/frs301_1_changeoffset.png)

After the header is changed:

![image](img/frs301_2_result.png)
