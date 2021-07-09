# lsdisk
List drives in Linux and show which slots drives are located.

Will list all discovered storage devices, and they're various metadata.
It will also enable showing where drives are located, as well as allow
for easy drive location if the enclosure allows it.

 * It uses LVM tools to find logical volumes: lvs, pvs, vgs
 * It uses md tools to find RAID arrays: mdadm
 * It uses megaraid tools to list HW RAID arrays: megaclisas-status
 * It uses NVMe CLI tools to list NVMe drives: nvme
 * It uses SAS tools to list SAS enclosures: sas2ircu
 * It uses LSI tools to list SAS enclosures: storcli64
 * It uses ZFS tools to list pools: zpool

Example /etc/lsdisk.conf

     # 12-bay enclosure
     ENCLOSURE[0:0]=\
     "2  5  8 11
      1  4  7 10
      0  3  6  9"
    
     # 4-bay enclosure amongst other drive bays on other systems
     ENCLOSURE[0:1]=\
     "X  X  X  X
      0  1  2  3
      X  X  X  X"
    
     # M.2 SATA drives
     ENCLOSURE[M2]=\
     " 0  1"
    
     # M.2 NVME drives
     ENCLOSURE[NVME]=\
     " 0  1"
    
     # SATA drive enclosure
     ENCLOSURE[SATA]=\
     " 0  1"
    
     # USB enclosure
     ENCLOSURE[USB]=\
     " 0  1"
