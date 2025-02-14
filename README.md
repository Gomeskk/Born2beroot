# Born2beroot

## Introduction

The **Born2beroot** project at 42 is designed to introduce students to system administration, focusing on setting up a secure Linux-based server. The project requires configuring a virtual machine (VM) with strict security measures, user management, and network configurations.

## Concept

The project involves installing and configuring Debian or Rocky, ensuring that the system adheres to security best practices while meeting specific requirements, including:

  - **User and group management** 

  - **Sudo and password policies** 

  - **UFW (Uncomplicated Firewall) setup** 

  - **SSH (Secure Shell) configuration** 

  - **LVM (Logical Volume Manager) partitioning**

  - **Monitoring scripts for system health**

## Mandatory Requirements

### Virtual Machine:

  - Install and configure a VM using VirtualBox.

  - Choose between **Debian** or **Rocky** as the operating system. (Debian is highly recommended
if you are new to system administration.)

### User Management:

  - Create a non-root user with sudo privileges.

  - Implement strong password policies to enforce security.

### Security Measures:

  - Configure UFW (Uncomplicated Firewall).

  - Set up and secure SSH (Secure Shell) access.

  - Disable root login over SSH.

### LVM Partitioning:

  - Use Logical Volume Manager (LVM) for flexible disk management.

  - Ensure proper partitioning for ```/home```, ```/var```, ```/srv``` and ```/tmp``` directories.

### Monitoring Script:

Develop a script that displays system information such as:

  - CPU Usage

  - Memory Usage

  - Disk Usage

  - Active Users

  - Running Services

  - Last Boot Time

### Hostname & Signature:

  - Set up a custom hostname following the 42 convention.

  - Configure a cron job to run the monitoring script at regular intervals.

## Bonus Features

  - Set up partitions correctly so you get a structure similar to the one below.

  - Set up a functional WordPress website with the following services: lighttpd, MariaDB, and PHP.

  - Set up a service of your choice that you think is useful (NGINX / Apache2 excluded!). During the defense, you will have to justify your choice.

## Implementation Steps

### 1. Setting Up the VM

  - Install VirtualBox or UTM and create a new VM.

   - Install **Debian** or **Rocky** as the operating system.

### 2. User & Group Management

  - Create a new user and assign necessary privileges.

  - Set up password policies using PAM (Pluggable Authentication Modules).

### 3. Configuring Security

  - Set up UFW to block all incoming traffic except SSH.

  - Disable SSH login for the root user.

  - Enable SSH key authentication (optional but recommended).

### 4. LVM Partitioning

  - Configure LVM to allocate space dynamically.

  - Create logical volumes for ```/home```, ```/var```, ```/srv```, ```/tmp```.

### 5. Monitoring Script

  - Write a bash script to display system metrics.

  - Set up a cron job to execute it every 10 minutes.

## Compilation and Usage

To run the monitoring script manually:

```console
bash monitoring.sh
```

To check system logs:

``` console
dmesg | tail -20
```

To check active users:

```console
who
```

To check available disk space:

```console
df -h
```

## Common Pitfalls

  - $\color{crimson}{\textbf{Incorrect LVM Partitioning:}}$ Ensure partitions are properly allocated.

  - $\color{crimson}{\textbf{Weak Password Policies:}}$ Use ```passwd``` and ```chage``` to enforce security rules.

  - $\color{crimson}{\textbf{Firewall Misconfiguration:}}$ Use ```sudo ufw status``` to verify active rules.

  - $\color{crimson}{\textbf{SSH Connectivity Issues:}}$ Check ```/etc/ssh/sshd_config``` for incorrect settings.

## Conclusion

The **Born2beroot** project is an introduction to Linux system administration, covering security, partitioning, and automation. It provides essential knowledge for managing real-world servers and implementing security best practices.
