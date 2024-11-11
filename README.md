# TwinCAT3_config
---
sidebar_position: 2
---

# TwinCAT3 (Windows)
---
## Table of Contents
1. [Introduction](#1-introduction)
2. [Install TwinCAT3](#2-install-twincat3)
3. [Configuration and Setup](#3-configuration-and-setup)
4. [Tips and Best Practices](#4-tips-and-best-practices)
---

You're reading the documentation for a development version. 


---

## 1. Introduction

TwinCAT 3 (The Windows Control and Automation Technology) is a development platform from Beckhoff that transforms any compatible PC into a real-time control system for managing various types of industrial automation systems, such as **PLC** (Programmable Logic Controller), motion control, robotics, and more.


## Install TwinCAT3 

This installation process can refer to the installation guide provideed on [Beckhoff official website.](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_installation/179473291.html&id=)


> **Tip:**
If you need to develop **using C++, please note the following**:
- The installation order should be: first install Visual Studio; and then install TwinCAT3.
:::


## 2. Connecting Computer to eRob

<div class="TwinCAT">
  <p>eRob Connection:</p>
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT1.png" alt="TwinCAT1" style={{ width: '500px', height: 'auto' }} />
  </a>
</div>

**The connection method can refer to the video ——>>>[Link](https://www.youtube.com/watch?v=5IJlLUlO148).**

## 3. Create TwinCAT Project

### 3.1 ESI File Placement

The name of the XML (ESI) configuration file for eRob is:

**ZeroErr Driver3.2.0.xml** ——>>>[Download link](https://en.zeroerr.cn/support/download/softwares/config-files)

The XML (ESI) file path for **Beckhoff TwinCAT3** is as follows:
`C:\TwinCAT\3.1\Config\Io\EtherCAT`

---
### 3.2 Creating a New Project in TwinCAT

After creating a new TwinCAT project, the first step is to ensure that the IP address connection is correct. The second step is to right-click on **"Devices"**, select the **"Scan"** option, and automatically scan for devices.

If the system cannot recognize the **`Driver1(ZeroErr Driver)`**, you need to install and select a compatible device using the following method:

<div class="TwinCAT">
  <p>**Check equipments compatible:**</p>
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT2.png" alt="TwinCAT2" style={{ width: '500px', height: 'auto' }} />
  </a>
</div>
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT3.png" alt="TwinCAT3" style={{ width: '900px', height: '400px' }} />
  </a>
</div>

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT4.png" alt="TwinCAT4" style={{ width: '300px', height: 'auto' }} />
  </a>
</div>

After automatically scanning for devices, to ensure that the axis can move properly, you need to configure the axis parameters. The configuration process can be referenced in `Chapter 6` of  `eRob CANopen and EtherCAT User Manual v1.9`.
[Download link for the manual](https://en.zeroerr.cn/support/download/manual)

---
### 3.3 Parameter Configuration
---
It is necessary to configure the parameters of each axis to ensure the correct movement.   
- 1. Unit configuration: In the navigation directory on the left go to the TwinCAT project > NC-Task 1-SAF > Axes > Axis 1 .   
a. Click the settings tab on the right.   
b. the desired unit of the axis.  

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT5.png" alt="TwinCAT5" style={{ width: '500px', height: 'auto' }} />
  </a>
</div>

---
- 2. Enc Parameter configuration
In the navigation directory on the left go to the TwinCAT project > NC-Task 1-SAF>Axes > Axis 1 > Enc.  
a. Click the Parameter tab on the right.   
b. Click the “Encoder Evaluation” arrow to view the options. The Scale Factor Numerator and Denominator values can be changed under the Offline Value.Set both Scaling Factor Numerator and Scaling Factor Denominator to 1, that is, when the master is under NCaxis control, it sends 1 unit, and the slave servo moves 1 encoder pulse position (plus).  

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT6.png" alt="TwinCAT6" style={{ width: '500px', height: 'auto' }} />
  </a>
</div>
---  
- 3. The parameters are activated
Click on the menu bar TwinCAT->Activate Configuration, and a prompt box will pop up, click “OK”. Online Value displays the modified value.
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT7.png" alt="TwinCAT7" style={{ width: '700px', height: 'auto' }} />
  </a>﻿# TwinCAT3_config

</div>
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT8.png" alt="TwinCAT8" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
---  
- 4. Motion parameter configuration

In the navigation directory on the left go to the TwinCAT project > NC-Task 1-SAF>Axes > Axis 1.   
a. Click the “Parameter” tab on the right.   
b. Click the,“Maximum Dynamics”,“Default Dynamics” and “Manual Motion andHoming” arrow to view the options.   
c. Modify value in the “Offline value”.  

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT9.png" alt="TwinCAT9" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>

---  
- 5. Monitoring Parameter configuration
In the navigation directory on the left go to the TwinCAT project > NC-Task 1-SAF >Axes > Axis 1.   
1）Click the Parameter tab on the right.   
2）Click the Monitoring arrow to view the options.   
3）In Offline value, modify the Monitoring.  

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT10.png" alt="TwinCAT10" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>

---
- 6. The parameters are activated
Click on the menu bar TwinCAT->Activate Configuration, and a prompt box will pop up, click OK. Online Value displays the modified value.  
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT11.png" alt="TwinCAT11" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
---

### 3.4 PDO Configuration
---
The specific operation steps of dynamic configuration of PDOby TwinCAT3master based on Beckhoff in this section are as follows.  
- 1. The cyclic data is visible in the PDO-assignment window for the Inputs and Outputs of the Sync Managers. The default PDO settings use the dynamic PDOs:“0x1600- RxPDOmapping parameter, 0x1A00-TxPDO mapping parameter.”
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT12.png" alt="TwinCAT12" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
---
- 2. TxPDO configuration: The TxPDO maps can be changed by selecting the desired TxPDO(0x1A00) and right
clicking in the PDO content window. Existing entries can be changed or deleted, and
new entries can be inserted between existing or appended to the end.

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT13.png" alt="TwinCAT13" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
--- 
- 3.A list of mappable objects is shown. The list only shows objects that can be mapped in the direction of
the map being changed. For example, attempting to insert an object on the input PDO 0x1A00 only
shows objects that can be mapped in the direction from the slave drive to the master controller.

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT14.png" alt="TwinCAT14" style={{ width: '350px', height: 'auto' }} />
  </a>
</div>
---
- 4. The inserted object appears in the PDO Content (0x1A00).

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT15.png" alt="TwinCAT15" style={{ width: '600px', height: 'auto' }} />
  </a>
</div>
---
- 5. The RxPDO maps can be changed by selecting the desired RxPDO(0x1600) and right clicking in the PDO content window. Existing entries can be changed or deleted, and new entries can be inserted between existing or appended to the end.

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT16.png" alt="TwinCAT16" style={{ width: '600px', height: 'auto' }} />
  </a>
</div>
---

- 6. A list of mappable objects is shown. The list only shows objects that can be mapped in the direction of the map being changed. For example, attempting to insert an object on the output PDO 0x1600 only shows objects that can be mapped in the direction from the controller to the drive.

<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT17.png" alt="TwinCAT17" style={{ width: '350px', height: 'auto' }} />
  </a>
</div>
---

- 7. The inserted object appears in the RxPDO Content (0x1600).

As the PDO map is changed, the startup script is automatically updated by TwinCATtosend to the slave drive during the PREOP to OP transition.The automatic link of the
DSP402 standard entries is only executed for axes which use standard object. With other modes of operation it is necessary to link the PDO’s manually.
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT18.png" alt="TwinCAT18" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
---
### 3.5 Motion Control

- 1. The operation mode of EtherCAT interface has to be selected between “SM-synchron” or “DC-synchron”. In this example “DC-synchron” is selected.
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT19.png" alt="TwinCAT19" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
- 2. Activate the configuration by clicking `Activate configuration`
- 3. Click `YES`.
- 4. Double click on the `Driver1(ZeroErr Driver)` . Navigate to “NC-Online” and click on “Set” in the Enabling menu. -> Click on `All` to set the enables
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT20.png" alt="TwinCAT20" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
- 5. Now input a target position and a target velocity and move the axis with the “F5”button tothe target position.click “F1, F2, F3, F4” to manually control the motor to run forward or
reverse at a fast or slow velocity. Click “F8” 
<div class="TwinCAT">
  <a href="https://en.zeroerr.cn/products/accessories/developmentkit" target="_blank">
    <img src="/img/TWINCAT21.png" alt="TwinCAT21" style={{ width: '700px', height: 'auto' }} />
  </a>
</div>
---  

## 4. PLC Programming

To control eRob using PLC programming, it is necessary to understand the relationship between the `NC axis`, `PLC axis`, and `physical axis` in TwinCAT. Additionally, the mapping relationship between the object dictionary and the NC axis can be configured according to the documentation provided on the [Beckhoff official website](https://infosys.beckhoff.com/english.php?content=../content/1033/tf50x0_tc3_nc_ptp/10650582539.html&id=9197998846476281621).   
Relationship diagram for reference only:

Here, a deep understanding of TwinCAT usage is required. If needed, additional configuration instructions will be provided later to ensure that eRob can be driven by connecting the NC axis via the PLC axis using the built-in functions in TwinCAT. A pre-configured program is provided [here](https://git.zeroerr.cn/Don/TC3_demo) as a reference.
