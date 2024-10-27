
# **Install Docker Desktop**
Minikube uses Docker to run Kubernetes clusters locally. Download and install **Docker Desktop** from the [official Docker page](https://www.docker.com/products/docker-desktop).

During the Docker installation:
- Choose **Use WSL 2 instead of Hyper-V**.
- Uncheck the option for creating a shortcut if you don’t need it.

After installation, **open Docker Desktop** and ensure that WSL2 integration is enabled.

### 4. **Check Docker Installation**
Open **Command Prompt (CMD)** or **PowerShell**, and check if Docker is installed correctly:

```bash
docker version
```

You should see the Docker version information displayed, confirming that Docker is running properly.

---

# **Install kubectl (Kubernetes CLI)**


 ### Downloading `kubectl` in PowerShell on Windows:

To interact with Kubernetes, install `kubectl`:

### Steps to Download and Set Up `kubectl`:

1. **Run the following command** to download `kubectl` using PowerShell:
   ```powershell
   curl.exe -LO "https://dl.k8s.io/release/$(curl.exe -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/windows/amd64/kubectl.exe"
   ```

   - Note: Using `curl.exe` instead of `curl` ensures you're using the native `curl` on Windows, which supports this syntax.

2. **Move the `kubectl` executable** to a directory in your system’s PATH, such as `C:\Windows\System32`:
   
   ```powershell
   Move-Item kubectl.exe C:\Windows\System32\
   ```

3. **Verify the installation**:
   After downloading and moving the file, verify `kubectl` is installed by checking its version:
   
   ```powershell
   kubectl version --client
   ```

This will display the client version of `kubectl`, confirming it has been installed correctly.

---


# Setting up **Minikube on Windows**:

## **Install Minikube**

1. **Create a Minikube directory**:
    ```powershell
    New-Item -Path 'C:\' -Name 'minikube' -ItemType Directory -Force
    ```

2. **Download Minikube**:
    ```powershell
    Invoke-WebRequest -OutFile 'C:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing
    ```

3. **Add Minikube to your PATH**:
    ```powershell
    $oldPath = [Environment]::GetEnvironmentVariable('Path', [EnvironmentVariableTarget]::Machine)
    if ($oldPath.Split(';') -inotcontains 'C:\minikube'){
      [Environment]::SetEnvironmentVariable('Path', $('{0};C:\minikube' -f $oldPath), [EnvironmentVariableTarget]::Machine)
    }
    ```

4. Verify Minikube installation:
    ```bash
    minikube version
    ```

### `Restart your pc`

before start minikube cluster, open your docker desktop. otherwise it shows failed!!

### 7. **Start Minikube**

To start Minikube with Docker as the driver, run the following command:

```bash
minikube start --driver=docker
```

Minikube will create a local Kubernetes cluster using Docker. This may take a few minutes, depending on your machine's resources.

### 8. **Verify the Minikube Cluster**

Once Minikube starts, check the status of the cluster:

```bash
minikube status
```

