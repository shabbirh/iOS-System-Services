iOS-System-Services
===================

![System Services Memory Screenshot](Sample Images/Screenshot.png "Memory and Disk Information")

This is a singleton class to gather all available information about a device.  It gives you over 75 methods to determine everything about a device, including: 
  * Hardware & Network Information
  * Battery Usage
  * Accelerometer Data
  * Disk Usage 
  * Running Processes
  * Memory Usage
  * And a complete UDID replacement based on unchanging device information.

Changes
===================

1.  Turned the class into a singleton, now accessible using this:  [systemServices sharedServices]
2.  Revamped the accelerometer information class - not a singleton, must alloc/init and start/stop
3.  Fixed network information bugs, with the exception of Cellular MAC address - it's incorrect most of the time for some reason (feel free to help out!)
4.  Fixed memory information bugs but memory methods are more of an estimate than fact.  We round to determine the most likely amount of memory on the device (feel free to change if you know a better way!)
5.  Upgraded speed!

Available Device Information
===================

```
// System Information

// Properties
    
    /* All System Information in Dictionary Format */
    NSDictionary *allSystemInformation;
    
    /* Hardware Information */
    
    // System Uptime (dd hh mm)
    NSString *systemsUptime;
    
    // Model of Device
    NSString *deviceModel;
    
    // Device Name
    NSString *deviceName;
    
    // System Name
    NSString *systemName;
    
    // System Version
    NSString *systemsVersion;
    
    // System Device Type (Not Formatted = iPhone1,0)
    NSString *systemDeviceTypeNotFormatted;
    
    // System Device Type (Formatted = iPhone 1)
    NSString *systemDeviceTypeFormatted;
    
    // Get the Screen Width (X)
    NSInteger screenWidth;
    
    // Get the Screen Height (Y)
    NSInteger screenHeight;
    
    // Get the Screen Brightness
    float screenBrightness;
    
    // Multitasking enabled?
    BOOL multitaskingEnabled;
    
    // Proximity sensor enabled?
    BOOL proximitySensorEnabled;
    
    // Debugger Attached?
    BOOL debuggerAttached;
    
    // Plugged In?
    BOOL pluggedIn;
    
    /* Jailbreak Check */
    
    // Jailbroken?
    int jailbroken;
    
    /* Processor Information */
    
    // Number of processors
    NSInteger numberProcessors;
    
    // Number of Active Processors
    NSInteger numberActiveProcessors;
    
    // Processor Speed in MHz
    NSInteger processorSpeed;
    
    // Processor Bus Speed in MHz
    NSInteger processorBusSpeed;
    
    /* Accessory Information */
    
    // Are any accessories attached?
    BOOL accessoriesAttached;
    
    // Are headphone attached?
    BOOL headphonesAttached;
    
    // Number of attached accessories
    NSInteger numberAttachedAccessories;
    
    // Name of attached accessory/accessories (seperated by , comma's)
    NSString *nameAttachedAccessories;
    
    /* Carrier Information */
    
    // Carrier Name
    NSString *carrierName;
    
    // Carrier Country
    NSString *carrierCountry;
    
    // Carrier Mobile Country Code
    NSString *carrierMobileCountryCode;
    
    // Carrier ISO Country Code
    NSString *carrierISOCountryCode;
    
    // Carrier Mobile Network Code
    NSString *carrierMobileNetworkCode;
    
    // Carrier Allows VOIP
    BOOL carrierAllowsVOIP;
    
    /* Battery Information */
    
    // Battery Level
    float batteryLevel;
    
    // Charging?
    BOOL charging;
    
    // Fully Charged?
    BOOL fullyCharged;
    
    /* Network Information */
    
    // Get Current IP Address
    NSString *currentIPAddress;
    
    // Get Current MAC Address
    NSString *currentMACAddress;
    
    // Get External IP Address
    NSString *externalIPAddress;
    
    // Get Cell IP Address
    NSString *cellIPAddress;
    
    // Get Cell MAC Address
    NSString *cellMACAddress;
    
    // Get Cell Netmask Address
    NSString *cellNetmaskAddress;
    
    // Get Cell Broadcast Address
    NSString *cellBroadcastAddress;
    
    // Get WiFi IP Address
    NSString *wiFiIPAddress;
    
    // Get WiFi MAC Address
    NSString *wiFiMACAddress;
    
    // Get WiFi Netmask Address
    NSString *wiFiNetmaskAddress;
    
    // Get WiFi Broadcast Address
    NSString *wiFiBroadcastAddress;
    
    // Connected to WiFi?
    BOOL connectedToWiFi;
    
    // Connected to Cellular Network?
    BOOL connectedToCellNetwork;
    
    /* Process Information */
    
    // Process ID
    int processID;
    
    // Process Name
    NSString *processName;
    
    // Process Status
    int processStatus;
    
    // Parent Process ID
    int parentPID;
    
    // List of process information including PID's, Names, PPID's, and Status'
    NSMutableArray *processesInformation;
    
    /* Disk Information */
    
    // Total Disk Space
    NSString *diskSpace;
    
    // Total Free Disk Space (Raw)
    NSString *freeDiskSpaceinRaw;
    
    // Total Free Disk Space (Percentage)
    NSString *freeDiskSpaceinPercent;
    
    // Total Used Disk Space (Raw)
    NSString *usedDiskSpaceinRaw;
    
    // Total Used Disk Space (Percentage)
    NSString *usedDiskSpaceinPercent;
    
    // Get the total disk space in long format
    long long longDiskSpace;
    
    // Get the total free disk space in long format
    long long longFreeDiskSpace;
    
    /* Memory Information */
    
    // Total Memory
    double totalMemory;
    
    // Free Memory (Raw)
    double freeMemoryinRaw;
    
    // Free Memory (Percent)
    double freeMemoryinPercent;
    
    // Used Memory (Raw)
    double usedMemoryinRaw;
    
    // Used Memory (Percent)
    double usedMemoryinPercent;
    
    // Active Memory (Raw)
    double activeMemoryinRaw;
    
    // Active Memory (Percent)
    double activeMemoryinPercent;
    
    // Inactive Memory (Raw)
    double inactiveMemoryinRaw;
    
    // Inactive Memory (Percent)
    double inactiveMemoryinPercent;
    
    // Wired Memory (Raw)
    double wiredMemoryinRaw;
    
    // Wired Memory (Percent)
    double wiredMemoryinPercent;
    
    // Purgable Memory (Raw)
    double purgableMemoryinRaw;
    
    // Purgable Memory (Percent)
    double purgableMemoryinPercent;
    
    /* Accelerometer Information */
    
    // Device Orientation
    UIInterfaceOrientation deviceOrientation;
    
    /* Localization Information */
    
    // Country
    NSString *country;
    
    // Language
    NSString *language;
    
    // TimeZone
    NSString *timeZoneSS;
    
    // Currency Symbol
    NSString *currency;
    
    /* Application Information */
    
    // Application Version
    NSString *applicationVersion;
    
    // Clipboard Content
    NSString *clipboardContent;
    
    /* Universal Unique Identifiers */
    
    // Unique ID
    NSString *uniqueID;
    
    // Device Signature
    NSString *deviceSignature;
    
    // CFUUID
    NSString *cfuuid;
```
Third-Pary Plugins
===================

A big thank you to the makers of:
  * Annotated Gauge iOS Class here: https://github.com/sabymike/MSSimpleGauge
  * Pie Chart iOS Class here: https://github.com/honcheng/iOSPlot
  * NSObject+PerformBlockAfterDelay iOS Class here: http://www.mikeash.com/pyblog/friday-qa-2009-08-14-practical-blocks.html

License
===================

Copyright © 2009-2013 Shmoopi LLC <shmoopillc@gmail.com> <http://www.shmoopi.net/>

This class and its usage are very intuitive and provide as simple an interface as possible for developers to plug into.  Please feel free to customize the class as much as you'd like, or use any of the code within your projects.  If you do add to the project, make sure to let me know so we can merge any changes.

If you like what you see here, or on our website, please feel free to drop us a line or purchase one of our applications!

~Shmoopi LLC
