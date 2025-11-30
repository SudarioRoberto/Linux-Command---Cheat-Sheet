# Linux Command Cheat Sheet

Quick reference for general Linux use and bioinformatics workflows (HPC + metagenomics)

---

## Navigation and File Management

```bash
pwd                       # Current directory
ls -al                    # List files with details
cd folder/                # Change directory
mkdir folder              # Create folder
cp file dest/             # Copy file
mv file dest/             # Move or rename file
rm file                   # Remove file
rm -rf folder             # Remove folder recursively (dangerous)
touch file.txt            # Create empty file
cat file                  # View file content
less file                 # Scroll through file
head file                 # First 10 lines
tail file                 # Last 10 lines
tail -f file              # Follow log updates
ls folder/*/              # List of files with details
```

## Hardware and System Information

```bash
dmesg                     # Kernel messages
cat /proc/cpuinfo         # CPU information
cat /proc/meminfo         # Memory information
free -h                   # Free and used memory
lsusb -tv                 # USB devices
lspci -tv                 # PCI devices
df -h                     # Disk usage overview
du -sh *                  # Folder sizes in current directory
top                       # Running processes live
```



## Search and Find Files

```bash
grep "text" file                 # Search text inside file
grep -r "text" folder/           # Recursive search
find . -name "*.fastq.gz"        # Find FASTQ files
```

## Compression Commands

```bash
gzip file.fastq                  # Compress
gunzip file.fastq.gz             # Decompress
tar -xvf archive.tar             # Extract .tar
tar -czvf file.tar.gz folder/    # Create .tar.gz
```

## Conda Environments

```bash
conda activate pig_metagenomics
conda deactivate
conda env list
```

## HPC and Slurm Scheduling

```bash
sbatch job.sbatch            # Submit job
squeue -u $USER              # My running jobs
scancel JOBID                # Cancel job
sinfo                        # View partitions
```

## FastQ Read Counting + QC

```bash
zcat file.fastq.gz | wc -l        # Count lines (divide by 4 for reads)
fastqc *.fastq.gz                 # Run FastQC on multiple files
multiqc .                         # Aggregate QC into 1 report
```

## Host Removal / Kneaddata Commands

**Standard paired-end command:**

```bash
kneaddata -i R1.fastq.gz -i R2.fastq.gz \
--reference-db pig_genome/ \
-o knead_out/ \
--trimmomatic trimmomatic_path \
--bowtie2 bowtie2_path
```

**Check host removal results:**

```bash
grep "Remaining reads" *.log
grep "Total reads after" -r knead_out/
```

## File Permissions

```bash
chmod +x script.sh           # Make executable
chmod 644 file               # Standard readable permissions
```

## Download and Integrity Check

```bash
wget URL                     # Download file
curl -O URL                 # Download file
sha256sum file               # Check file integrity
```

## ⚠️ Safety Reminders

```bash
rm -rf /                     # Never run this
sudo anything                # Avoid on HPC
```

---

*Last updated: November 2025*
