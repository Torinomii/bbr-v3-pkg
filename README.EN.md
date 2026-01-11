# bbr-v3-pkg

[![Build Package](https://github.com/Zxilly/bbr-v3-pkg/actions/workflows/build.yml/badge.svg)](https://github.com/Zxilly/bbr-v3-pkg/actions/workflows/build.yml)

Compile Linux kernel with BBRv3 support into deb package formats.

## Installation

Download from `https://github.com/Zxilly/bbr-v3-deb/releases/latest`.

For Debian/Ubuntu systems, download the `linux-headers-*.deb` and `linux-image-*.deb` files and install using `dpkg -i` or `apt install`.


## Configuration

### Enabling BBRv3

```bash
# Set up BBRv3
echo 'net.ipv4.tcp_congestion_control=bbr' | sudo tee -a /etc/sysctl.conf
sudo sysctl -p

# Check the current TCP congestion control algorithm
sysctl net.ipv4.tcp_congestion_control

# Check available TCP congestion control algorithms; algorithms compiled as modules will not be displayed
sysctl net.ipv4.tcp_available_congestion_control
```

To enable BBRv3, set the congestion control algorithm to `bbr`. If you want to use an earlier version of BBR, set the congestion control algorithm to `bbr1`.
