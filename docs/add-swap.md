# Add Emergency Swap

Swap helps with short-term memory pressure but does not replace RAM.

```bash
ls -lh /swapfile
sudo fallocate -l 512M /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
free -h
```

Make it persistent (add only once):

```bash
grep -n "/swapfile" /etc/fstab
echo "/swapfile none swap sw 0 0" | sudo tee -a /etc/fstab
```

Check disk space with `df -h /` before creating the file.