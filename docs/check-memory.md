# Check Free Memory

## Quick overview

```bash
free -h
```

Look at the **available** column. It shows memory that can be used
without swapping, and it matters more than the **free** column.

## Check swap

```bash
swapon --show
```

No output means no swap is active.

## Find which processes use the most memory

```bash
ps aux --sort=-%mem | head -n 10
```

## Detailed memory info

```bash
cat /proc/meminfo | head -n 5
vmstat 1 5
```

## Live view

```bash
top        # press M to sort by memory, q to quit
```

## Check disk space too

Low disk space often shows up together with low memory.

```bash
df -h /
sudo du -xhd1 /var 2>/dev/null
sudo journalctl --disk-usage
```

## Check for stuck package processes

```bash
ps aux | grep -E "apt|dpkg"
```

Do not kill package processes or delete lock files until you know what they are.