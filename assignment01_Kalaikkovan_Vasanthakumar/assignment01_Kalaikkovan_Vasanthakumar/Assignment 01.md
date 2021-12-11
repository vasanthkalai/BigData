---
title: Assignment 1
subtitle: Computer performance, reliability, and scalability calculation
author: Kalaikkovan Vasanthakumar

---

## 1.2 

### a. Data Sizes

| Data Item                                  | Size per Item | 
|--------------------------------------------|--------------:|
| 128 character message.                     | 128 Bytes     |
| 1024x768 PNG image                         | 1 MB          |
| 1024x768 RAW image                         | 7.5 MB        | 
| HD (1080p) HEVC Video (15 minutes)         | 36 MB         |
| HD (1080p) Uncompressed Video (15 minutes) | 36000 MB      |
| 4K UHD HEVC Video (15 minutes)             | 228 MB        |
| 4k UHD Uncompressed Video (15 minutes)     | 228000 MB     |
| Human Genome (Uncompressed)                | 1.5 GB        |

1. Character = 8 bits(1 byte).

2. Number of pixels for 1024*768=786,432 pixels. 
    Total file size 786,432*3=2,359,296 bytes= 2,359296/1024/1024=2.25MB and PNG is compressed, we can use a typical compression ratio of 2, then the size would be 1 MB.

3. Raw image has a depth of 10, then it is 1024 * 768 * 10/1024/1024 = 7.5MB

4. Using 30 fps and 8 bit depth, we have 15 miniutes = 15* 60 seconds = 900 seconds.
    HEVC is known to have a common compression ratio of 1000
    15 minutes HEVC video = 900*30*1290*1080*8/8/1000/1024/1024 = ~ 36 MB.
    
5. For uncompressed video, the size will be 1000 times more than the number in 4, that makes it 36,000 MB.

6. For 4k, the size of 15 mins HEVC video will be: 900*30*4096*2160*8/8/1000/1024/1024 = ~ 228 MB.

7. If uncompressed, the size is about 1000 times larger, which is about 228,000 MB. 

8. 6*10^9 base pairs/diploid genome x 1 byte/4 base pairs = 1.5GB

### b. Scaling

|                                           | Size     | # HD | 
|-------------------------------------------|---------:|-----:|
| Daily Twitter Tweets (Uncompressed)       | 64 GB    |   1  |
| Daily Twitter Tweets (Snappy Compressed)  | 43 GB    |   1  |
| Daily Instagram Photos                    | 75 TB    |  23  |
| Daily YouTube Videos                      | 104 TB   |  32  |
| Yearly Twitter Tweets (Uncompressed)      | 23 TB    |   7  |
| Yearly Twitter Tweets (Snappy Compressed) | 15 TB    |   5  |
| Yearly Instagram Photos                   | 27375 TB | 8213 |
| Yearly YouTube Videos                     | 37960 TB |11388 |

1. Approx 500 million tweets are sent per day, 
    Uncompressed daily storage = 500 million*128 bytes = 64,000,000,000 bytes (64 GB).

2. Snappy compression has a 1.5-1.7x ratio for plain text, if we use 1.5
    then storage for compressed data = 43 GB.

3. Daily Instagram photos: 
    storage size is 0.75 * 100,000,000 * 1MB = 75,000,000 MB (75 TB).

4. Daily YouTube Videos:
    The daily video is 500 hours * 60 * 24 = 720000 hours = 720000 * 60 minutes = 720000 * 4 per 15 minutes length. 
    So the storage is about 720000 * 4 * 36 MB = 103,680,000 MB, (104 TB).

5. 64 GB * 365 = 23,360 GB = 23 TB.

6. 43 GB * 365 = 15,695 GB = 15 TB.

7. 75 TB * 365 = 27,375 TB.

8. 104 TB * 365 = 37,960 TB.

### c. Reliability
|                                    | # HD | # Failures |
|------------------------------------|-----:|-----------:|
| Twitter Tweets (Uncompressed)      |   7  |less than 1 |
| Twitter Tweets (Snappy Compressed) |   5  |less than 1 |
| Instagram Photos                   | 8213 |   73       |
| YouTube Videos                     |11388 |  101       |

The failure rate used is 0.89%. 
#Failures = #HD * Failure_Rate

### d. Latency

|                           | One Way Latency      |
|---------------------------|---------------------:|
| Los Angeles to Amsterdam  | 30 ms                |
| Low Earth Orbit Satellite | 40 ms                |
| Geostationary Satellite   | 600 ms               |
| Earth to the Moon         | 1281 ms              |
| Earth to Mars             | 3 minutes            | 

1. The distance between LA and Amsterdam is 8937 km, and the speed of light is about 300,000 km/.
    Time = 8937 * 1000/300000 = 29.79 ms = ~30 ms. 

4. The distance between earth and moon is 384,400 km, the speed of light is 300,000 km/s 
    Time = 384,400/300,000 * 1000 = 1281.3 ms

5. The distance between earth and Mars is about 54.6 million kilometers, 
    Time = 54,600,000/300,000 s = 182 s = 3 minutes
