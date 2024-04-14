# FU Secathon Writeup

2021 - Forensics category - FRS401

## Brief

In the tcp stream, there is a notable *png header* datas (*PNG*, *IHDR*,...). We can manually extract the file raw data, or we can just use a file carving tool such as *foremost* to carve the file out.

[Download file here ⬇](dump.pcap)

## Details

### Get file manually

Open the pcap file in *Wireshark* and follow the TCP stream. View the stream in raw and copy the data.

![image](https://user-images.githubusercontent.com/80664686/138729927-b5f34b02-c533-40d3-80fb-fc20ea95a49d.png)

Open *HxD*, create a new file and paste the copied data into HxD. Find the PNG header, identify where the image start and end then delete all the rest.

![image](https://user-images.githubusercontent.com/80664686/138731523-1c23c305-51f2-4fa8-b0da-7de46fef6fa5.png)

> Flag: FUSEC{39eea648dab96b0ee6022dabb38bc420}

### Get file using file carving tool

The simplest method to solve is using a file carving tool such as `foremost`.

```console
$ foremost dump.pcap
Processing: dump.pcap
|*|

$ tree output/
output/
├── audit.txt
└── png
    └── 00002130.png

1 directory, 2 files
```

**00002130.png**

![image](https://user-images.githubusercontent.com/80664686/138735373-04bad459-2d54-4446-b71b-ee938317cbf7.png)
