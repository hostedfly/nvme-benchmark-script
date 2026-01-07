# NVMe Benchmark Script

This is a simple checklist and guide to verify if your hosting provider is giving you **Real NVMe Performance** or capping your I/O speeds.

At **[HostedFly](https://www.hostedfly.com)**, we believe in transparency. Use this method to test your server's true speed.

## Prerequisites
You need `fio` installed on your Linux server.

```bash
# Ubuntu / Debian
apt-get install fio -y

# CentOS / AlmaLinux
yum install fio -y

How to Test
Run the following command to check random read/write performance:

fio --randrepeat=1 --ioengine=libaio --direct=1 --gtod_reduce=1 --name=test --filename=test --bs=4k --iodepth=64 --size=1G --readwrite=randrw --rwmixread=75

## Expected Results

SATA SSD: ~300-500 MB/s
Fake NVMe (Capped): ~400-600 MB/s
Real NVMe (HostedFly Standard): 1000 MB/s +

If you are getting low speeds, your "noisy neighbors" might be stealing your resources.

Maintained by the HostedFly Engineering Team.
