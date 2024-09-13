---
title: RAID
draft: false
tags:
  - system-design
  - availability
---
#### RAID0

- **Configuration**: Two identical hard drives.
- **Feature**: Uses 'striping' to partition data across both drives, doubling the data write rate.

#### RAID1

- **Configuration**: Two identical hard drives.
- **Feature**: Mirrors data across both drives, providing redundancy and parallel data writing with minimal overhead.

#### RAID10

- **Configuration**: Combines RAID0 and RAID1 across four identical hard drives.
- **Feature**: Data is both mirrored and striped, offering benefits of both RAID0 and RAID1.

#### RAID5

- **Configuration**: Multiple drives.
- **Feature**: Uses one drive's worth of space for redundancy, providing fault tolerance with less overhead compared to RAID1.

#### RAID6

- **Configuration**: Similar to RAID5 but with additional redundancy.
- **Feature**: Requires one more drive than RAID5, offering extra protection against data loss. 