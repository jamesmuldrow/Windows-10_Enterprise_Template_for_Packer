# Windows 10 Enterprise Template for Packer

### Introduction 

This repository contains Windows 10 Enterprise Template that can be used to create boxes for VMWare using Packer ([Website](http://www.packer.io)) ([Github](http://github.com/jamesmuldrow/packer)).

### Windows Editions

This repo currently tested to support the following Windows Editions:

- en_windows_10_business_editions_version_1909_x64_dvd_ada535d0

### Requirements

- Mac running VMWare Fusion 
- Packer installed
- en_windows_10_business_editions_version_1909_x64_dvd_ada535d0.iso

### Getting Started

1. Clone and change directory into this repo
2. Copy .variables.example.json to variables.json
3. Place downloaded iso file in ./iso folder
4. Run the following command:
````
packer build -var-file=variables.json windows10.json
````

### Contributing

Pull requests welcomed.

### References

This repo references code from ([Joe Fitzgerald's Github](https://github.com/joefitzgerald/packer-windows))