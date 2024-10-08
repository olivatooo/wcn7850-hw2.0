# wcn7850 hw2.0 for arch linux

## If your wcn7850 hw2.0 atk12 does not show up in dmesg try a CMOS Reset!


Fix for WIFI not working in my MS-7E25/MAG Z790 TOMAHAWK MAX WIFI (MS-7E25), BIOS A.50 04/26/2024 in my archlinux.

Basically I'm just using old atk11 drivers instead of atk12h.

No, newer kernels and newers firmwares `don't work` with this motherboard. That's why I created this repository, to fix this exact problem. Tested in `6.11.2-arch1-1`

## Is this repository for me?


Check your dmesg, if it recognizes your wifi card, but your wifi does not work. Yes, its for you.

## How to check?

```sh
sudo dmesg | grep -i ath12
```

If it returns `ath12k_pci 0000:04:00.0: Hardware name: wcn7850 hw2.0` and your wifi does not work, then yes, this is for you.



How to use:

```sh 
git clone https://github.com/olivatooo/wcn7850-hw2.0
```

```sh 
cd wcn7850-hw2.0
```

If you want to do a backup first, your call. I don't care usually


```sh 
cp -r /lib/firmware/ath12k ath12k-old
```

Move the outdated drivers that work.

```sh 
cp -r ath12k /lib/firmware
```


The end result should be like this:

```
/lib/firmware/ath12k/WCN7850/hw2.0
```

Thanks https://github.com/kvalo/ath11k-firmware/ for the firmware. But sadly it's off now
