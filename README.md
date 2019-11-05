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
````bash
git clone https://github.com/jamesmuldrow/Windows-10_Enterprise_Template_for_Packer.git
cd Windows-10_Enterprise_Template_for_Packer.git
````
2. Copy .variables.example.json to variables.json
````bash
cp .variables.example.json variables.json
````
3. Modify lines 88, 89 & 109, 110 in the autounnattend.xml file.
    - 88, 89 & 109,110 both look like this:  
````xml
<Value>TQBhAHIAaQBuAGUAcwAxAFAAYQBzAHMAdwBvAHIAZAA=</Value>
<PlainText>false</PlainText>

````
Change them to
````xml
<Value>Your Plain Text Password Goes Here</Value>
<PlainText>true</PlainText>
````

4. Modify the "ssh_password" field in variables.json to reflect user password we modified in step 3.
5. Place downloaded iso file in ./iso folder
6. Run the following command:
````bash
packer build -var-file=variables.json windows10.json
````

Once complete, your resulting VM will be stored in the ./output-vmware-iso directory

Successful completion will look like this: 
````output
==> Builds finished. The artifacts of successful builds are:
--> vmware-iso: VM files in directory: output-vmware-iso
````
### Contributing

Pull requests welcomed.

### References

This repo references code from ([Joe Fitzgerald's Github](https://github.com/joefitzgerald/packer-windows))