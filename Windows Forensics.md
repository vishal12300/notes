## Introduction to Computer Forensics for Windows:

Computer forensics is an essential field of cyber security that involves gathering evidence of activities performed on computers. It is a part of the wider Digital Forensics field, which deals with forensic analysis of all types of digital devices, including recovering, examining, and analyzing data found in digital devices. The applications of digital and computer forensics are wide-ranging, from the legal sphere, where it is used to support or refute a hypothesis in a civil or criminal case, to the private sphere, where it helps in internal corporate investigations and incident and intrusion analysis.


## Forensic Artifacts:

When performing forensic analysis, you will often hear the word 'artifact'. Forensic artifacts are essential pieces of information that provide evidence of human activity. For example, during the investigation of a crime scene, fingerprints, a broken button of a shirt or coat, the tools used to perform the crime are all considered forensic artifacts. All of these artifacts are combined to recreate the story of how the crime was committed. 

## Windows Registry:

The Windows Registry is a collection of databases that contains the system's configuration data. This configuration data can be about the hardware, the software, or the user's information.

## Structure of the Registry:

The registry on any Windows system contains the following five root keys:
```
HKEY_CURRENT_USER
HKEY_HKEY_USERS
HKEY_LOCAL_MACHINE
HKEY_CLASSES_ROOT
HKEY_CURRENT_CONFIG
```

You can view these keys when you open the regedit.exe utility via run the following command in CMD or run 
``` regedit.exe ```

## Offline Registry hive stored 
Registry hives are located on the disk. The majority of these hives are located in the ``` C:\Windows\System32\Config ``` directory and are:

```
DEFAULT (mounted on HKEY_USERS\DEFAULT)
SAM (mounted on HKEY_LOCAL_MACHINE\SAM)
SECURITY (mounted on HKEY_LOCAL_MACHINE\Security)
SOFTWARE (mounted on HKEY_LOCAL_MACHINE\Software)
SYSTEM (mounted on HKEY_LOCAL_MACHINE\System)
NTUSER.DAT (mounted on HKEY_CURRENT_USER when a user logs in)
USRCLASS.DAT (mounted on HKEY_CURRENT_USER\Software\CLASSES)
```

#### The Amcache Hive:
Apart from these files, there is another very important hive called the AmCache hive. This hive is located in ``` C:\Windows\AppCompat\Programs\Amcache.hve ```. Windows creates this hive to save information on programs that were recently run on the system.

## Transaction Logs and Backups:
Some other very vital sources of forensic data are the registry transaction logs and backups. The transaction logs can be considered as the journal of the changelog of the registry hive. Windows often uses transaction logs when writing data to registry hives. The transaction log for each hive is stored as a .LOG file in the same directory as the hive itself. For example, the transaction log for the SAM hive will be located in ``` C:\Windows\System32\Config ``` in the filename SAM.LOG.
These are the backups of the registry hives located in the C:\Windows\System32\Config directory. These hives are copied to the ``` C:\Windows\System32\Config\RegBack ```  directory every ten days. It might be an excellent place to look if you suspect that some registry keys might have been deleted/modified recently.

## Data Acquisition
This process is called data acquisition. Below we discuss different ways to acquire registry data from a live system or a disk image. 
For acquiring these files, we can use one of the following tools:
* KAPE [https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape](https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape)
* Autopsy [https://www.autopsy.com/](https://www.autopsy.com/)
* FTK Imager [https://www.exterro.com/ftk-imager](https://www.exterro.com/ftk-imager)

## Exploring Windows Registry
Once we have extracted the registry hives, we need a tool to view these files as we would in the registry editor. Since the registry editor only works with live systems and can't load exported hives, we can use the following tools:
* AccessData's Registry Viewer: [https://accessdata.com/product-download/registry-viewer-2-0-0](https://accessdata.com/product-download/registry-viewer-2-0-0)
* Zimmerman's Registry Explorer: [https://ericzimmerman.github.io/#!index.md](https://ericzimmerman.github.io/#!index.md)
* RegRipper [https://github.com/keydet89/RegRipper3.0](https://github.com/keydet89/RegRipper3.0)


