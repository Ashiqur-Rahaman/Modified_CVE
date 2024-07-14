# CVE-2022-21661 Scanner

This project contains a Go script to scan for the WordPress CVE-2022-21661 vulnerability. The script can scan a single IP address or a list of IP addresses and logs the results.

## Prerequisites

- Go 1.19 (Due to compatibility issues with later versions)

## Installation

### Downgrade Go Version (if needed)

If you are currently using a version of Go later than 1.19, follow these steps to install Go 1.19:

1. **Remove the current Go version:**

    ```sh
    sudo rm -rf /usr/local/go
    ```

2. **Download and install Go 1.19:**

    ```sh
    wget https://go.dev/dl/go1.19.13.linux-amd64.tar.gz
    sudo tar -C /usr/local -xzf go1.19.13.linux-amd64.tar.gz
    export PATH=$PATH:/usr/local/go/bin
    ```

3. **Add Go to your path:**

    You may want to add the `export PATH` line to your `.bashrc` or `.profile` to make it permanent:

    ```sh
    echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
    source ~/.bashrc
    ```

### Setting Up the Project

1. **Clone the repository:**

    ```sh
    git clone https://github.com/your-repo/cve-2022-21661-scanner.git
    cd cve-2022-21661-scanner
    ```

2. **Initialize Go modules:**

    ```sh
    go mod init your-module-name
    ```

3. **Add required dependencies:**

    ```sh
    go get github.com/gookit/color@v1.4.3
    go get github.com/imroc/req/v3@v3.12.0
    ```

4. **Ensure dependencies are tidy:**

    ```sh
    go mod tidy
    ```

## Usage

You can run the script in two modes: scanning a single IP or scanning a list of IPs from a file.

### Scan a Single IP

To scan a single IP, use the `-h` flag followed by the IP address:

```sh
sudo go run CVE-2022-21661.go -h <single_ip>
