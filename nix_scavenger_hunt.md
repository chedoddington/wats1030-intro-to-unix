# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. 

*Paste the output of the `pwd` command here:* 
	/Users/che/wats1030-intro-to-unix

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
	LICENSE				challenge_files				
	nix_scavenger_hunt_stretch.md
	README.md			nix_scavenger_hunt.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
	The results show more information about each file - including the author, date and 	time: 
	total 40
	drwxr-xr-x    8 che  staff   272B Aug 13 08:11 .
	drwxr-xr-x+  16 che  staff   544B Aug 13 08:06 ..
	drwxr-xr-x   13 che  staff   442B Aug 13 08:04 .git
	-rw-r--r--    1 che  staff   1.1K Aug 13 08:04 LICENSE
	-rw-r--r--    1 che  staff   1.3K Aug 13 08:04 README.md
	drwxr-xr-x  111 che  staff   3.7K Aug 13 08:04 challenge_files
	-rw-r--r--@   1 che  staff   5.4K Aug 13 08:11 nix_scavenger_hunt.md
	-rw-r--r--    1 che  staff   317B Aug 13 08:04 nix_scavenger_hunt_stretch.md

* The `man` ("manual") command tells you more about how any given command works. Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
	-a shows the directory entries whose names begin with a dot
	-l (The lowercase letter ``ell''.)  List in long format.  (See below.)  If the 	
	output is to a terminal, a total sum for all the file sizes is output on a line 
	before the long listing.
	-h When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte, 
	Gigabyte, Terabyte and Petabyte in order to reduce the number of digits to three 
	or less using base 2 for sizes.

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
	Applications			bin				net
	Library				cores				private
	Network				dev				sbin
	System				etc				tmp
	Users				home				usr
	Volumes				installer.failurerequests	var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
	/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
	/Users/che

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
	3

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
	/Users/che/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?*
	It showed the last command that I entered.

* Press the up arrow a few more times. *What do you see?*
	It shows all of the commands that I have previously entered.

* Run the `history` command. *What do you see?*
	I see a numbered list of all of the commands that I have previously entered.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
	che

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
	no one else :(
	
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
	 8:26  up 1 day, 12:23, 2 users, load averages: 0.90 1.06 1.13

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
	It shows a list of processes running along with information about them. It shows 	how long they’ve been running, the percentage of CPU they’re using, how much 	
	memory they’re using, who is running the process, etc.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
	This shows the same processing running, but in real time. It refreshes itself 
	every few seconds.
	

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
	2

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
	1-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
	./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
	2

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
	./serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo 
	sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt 
	incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.


### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
	The output of the ls command was written into files.txt instead of to the screen.

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
	I see the same files, however, now I can use my up and down arrow keys to scroll 
	through them. I’m also now seeing them one page at a time.
	
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

	Last login: Thu Aug 13 07:56:55 on ttys000
Addaches-MacBook-Pro:~ che$ ps aux | grep "che "
che              2228   1.4  1.1  2738132  94892   ??  S     7:56AM   0:51.69 /Applications/Utilities/Terminal.app/Contents/MacOS/Terminal
che               668   0.4  1.2  4278512  98064   ??  Ss   Tue08PM   0:22.74 /System/Library/Frameworks/WebKit.framework/Versions/A/XPCServices/com.apple.WebKit.WebContent.xpc/Contents/MacOS/com.apple.WebKit.WebContent
che               395   0.1  0.3  2653672  24564   ??  S    Tue08PM   1:18.18 /System/Library/CoreServices/NotificationCenter.app/Contents/MacOS/NotificationCenter
che              2294   0.1  0.7  2616384  61648   ??  S     8:07AM   0:32.22 /Applications/TextEdit.app/Contents/MacOS/TextEdit
che              2425   0.0  0.1  2494888   7564   ??  S     8:40AM   0:00.12 /System/Library/PrivateFrameworks/AOSKit.framework/Versions/A/XPCServices/com.apple.iCloudHelper.xpc/Contents/MacOS/com.apple.iCloudHelper
che              2310   0.0  0.0  2493356   2824   ??  S     8:09AM   0:00.02 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/PrintCore.framework/Versions/A/printtool agent
che              2305   0.0  0.3  2573072  24644   ??  Us    8:08AM   0:00.47 /System/Library/Frameworks/AppKit.framework/Versions/C/XPCServices/DocumentPopoverViewService.xpc/Contents/MacOS/DocumentPopoverViewService
che              2298   0.0  0.1  2492840   5512   ??  S     8:07AM   0:00.01 /System/Library/PrivateFrameworks/HelpData.framework/Versions/A/Resources/helpd
che              2265   0.0  0.0  2469876   3348   ??  S     8:00AM   0:00.03 /usr/bin/ssh-agent -l
che              2239   0.0  1.4  3803728 116872   ??  Ss    7:58AM   0:08.27 /System/Library/Frameworks/Foundation.framework/Versions/C/XPCServices/LookupViewService.xpc/Contents/MacOS/LookupViewService
che              2231   0.0  0.0  2461020   1340 s000  S+    7:56AM   0:00.15 -bash
che              2221   0.0  0.6  3274376  54132   ??  S     7:55AM   0:00.65 /Applications/Google Chrome.app/Contents/Versions/44.0.2403.155/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --enable-deferred-image-decoding --lang=en-US --force-fieldtrials=AffiliationBasedMatching/Enabled/AudioProcessing48kHzSupport/Default/*AutofillEnabled/Default/*AutofillFieldMetadata/Enabled/BackgroundRendererProcesses/Disallow/CaptivePortalInterstitial/Enabled/*ChildAccountDetection/Disabled/ChromeDashboard/Default/*DomRel-Enable/enable/*EmbeddedSearch/Group7 pct:10g stable:pp2 prefetch_results:1 reuse_instant_search_base_page:1/*EnhancedBookmarks/Default/*ExtensionContentVerification/Enforce/*ExtensionDeveloperModeWarning/Default/*ExtensionInstallVerification/None/FlashHardwareVideoDecode/HwVideo/*GoogleNow/Enable/*IconNTP/Default/*NewProfileManagement/Enabled/NewVideoRendererTrial/Enabled/*OmniboxBundledExperimentV1/Unused_2/*PasswordGeneration/Disabled/PasswordLinkInSettings/Enabled/PasswordManagerUI/Infobar/PermissionBubbleRollout/Enabled/PrerenderFromOmnibox/OmniboxPrerenderEnabled/*QUIC/EnabledNoIdForLargePopulation/*RefreshTokenDeviceId/Enabled/*RememberCertificateErrorDecisions/Default/ReportCertificateErrors/ShowAndPossiblySend/*ReportCertificateErrorsOverHttp/UploadReportsOverHttp/SHA1IdentityUIWarning/Enabled/SHA1ToolbarUIJanuary2016/Warning/SHA1ToolbarUIJanuary2017/Error/*SafeBrowsingIncidentReportingService/Default/*SdchPersistence/Default/SessionRestoreBackgroundLoading/Restore/*SettingsEnforcement/no_enforcement/SyncBackingDatabase32K/Enabled/*UMA-Dynamic-Binary-Uniformity-Trial/default/*UMA-Dynamic-Uniformity-Trial/Group3/*UMA-Population-Restrict/normal/*UMA-Uniformity-Trial-1-Percent/group_98/*UMA-Uniformity-Trial-10-Percent/group_05/*UMA-Uniformity-Trial-100-Percent/group_01/*UMA-Uniformity-Trial-20-Percent/group_02/*UMA-Uniformity-Trial-5-Percent/group_19/*UMA-Uniformity-Trial-50-Percent/default/*UseDelayAgnosticAEC/DefaultDisabled/*VoiceTrigger/Install/ --extension-process --enable-webrtc-hw-h264-encoding --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --enable-pinch-virtual-viewport --enable-delegated-renderer --num-raster-threads=2 --gpu-rasterization-msaa-sample-count=8 --use-image-texture-target=3553 --channel=2212.2.147985360
che              2219   0.0  0.1  2493288   5820   ??  Us    7:55AM   0:00.02 /System/Library/Frameworks/VideoToolbox.framework/Versions/A/XPCServices/VTDecoderXPCService.xpc/Contents/MacOS/VTDecoderXPCService
che              2217   0.0  0.9  2788392  74880   ??  S     7:55AM   0:11.65 /Applications/Google Chrome.app/Contents/Versions/44.0.2403.155/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=gpu-process --channel=2212.0.1452592794 --supports-dual-gpus=false --gpu-driver-bug-workarounds=16,26,31,33,42,45,52,58 --gpu-vendor-id=0x8086 --gpu-device-id=0x162b --gpu-driver-vendor --gpu-driver-version
che              2215   0.0  0.1  2453580   5256   ??  S     7:55AM   0:00.01 /Applications/Google Chrome.app/Contents/Versions/44.0.2403.155/Google Chrome Framework.framework/Helpers/crashpad_handler --database=/Users/che/Library/Application Support/Google/Chrome/Crashpad --url=https://clients2.google.com/cr/report --annotation=plat=OS X --annotation=prod=Chrome_Mac --annotation=ver=44.0.2403.155 --handshake-fd=7
che              2212   0.0  1.9  3319616 158308   ??  S     7:55AM   0:35.02 /Applications/Google Chrome.app/Contents/MacOS/Google Chrome
che              2157   0.0  0.1  2468896   5284   ??  Ss    7:26AM   0:00.01 /System/Library/Frameworks/ApplicationServices.framework/Versions/A/Frameworks/HIServices.framework/Versions/A/XPCServices/com.apple.hiservices-xpcservice.xpc/Contents/MacOS/com.apple.hiservices-xpcservice
che              2136   0.0  0.5  2630696  38168   ??  Ss    7:18AM   0:01.63 /System/Library/Frameworks/AppKit.framework/Versions/C/XPCServices/com.apple.appkit.xpc.openAndSavePanelService.xpc/Contents/MacOS/com.apple.appkit.xpc.openAndSavePanelService
che              2131   0.0  2.6  3974188 222108   ??  S     7:18AM   0:43.53 /Applications/Numbers.app/Contents/MacOS/Numbers
che              2120   0.0  0.2  2496116  17100   ??  S     7:05AM   0:00.13 /System/Library/PrivateFrameworks/Notes.framework/Versions/A/XPCServices/com.apple.NotesMigratorService.xpc/Contents/MacOS/com.apple.NotesMigratorService
che              2085   0.0  0.1  2579308  10604   ??  S     6:44AM   0:00.96 /System/Library/Image Capture/Support/Image Capture Extension.app/Contents/MacOS/Image Capture Extension
che              2084   0.0  0.0  2471352   2608   ??  Ss    6:44AM   0:00.02 /System/Library/Image Capture/Devices/PTPCamera.app/Contents/XPCServices/apple.DevicePropertyReader.xpc/Contents/MacOS/apple.DevicePropertyReader
che              2083   0.0  0.1  2558460  10948   ??  S     6:44AM   0:01.31 /System/Library/Image Capture/Devices/PTPCamera.app/Contents/MacOS/PTPCamera
che              1909   0.0  0.2  2542188  15356   ??  S    12:07AM   0:00.30 /System/Library/PrivateFrameworks/Noticeboard.framework/Versions/A/Resources/nbagent.app/Contents/MacOS/nbagent
che              1757   0.0  0.1  2470292   7216   ??  Ss    4:33PM   0:00.17 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/XPCServices/com.apple.CommerceKit.TransactionService.xpc/Contents/MacOS/com.apple.CommerceKit.TransactionService
che              1645   0.0  0.2  2531196  14736   ??  S    12:43PM   0:00.18 /System/Library/PrivateFrameworks/MailService.framework/Versions/A/XPCServices/com.apple.MailServiceAgent.xpc/Contents/MacOS/com.apple.MailServiceAgent
che              1641   0.0  0.0  2493764   2556   ??  Ss   12:43PM   0:00.08 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.ComponentHelper.xpc/Contents/MacOS/com.apple.audio.ComponentHelper
che              1640   0.0  0.1  2469456   4808   ??  Ss   12:43PM   0:00.03 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.SandboxHelper.xpc/Contents/MacOS/com.apple.audio.SandboxHelper
che              1638   0.0  0.1  2493540   5136   ??  S    12:43PM   0:00.06 /System/Library/PrivateFrameworks/CharacterPicker.framework/Versions/A/XPCServices/com.apple.CharacterPicker.FileService.xpc/Contents/MacOS/com.apple.CharacterPicker.FileService
che              1634   0.0  0.8  4125708  64436   ??  S    12:42PM   0:13.08 /Applications/Messages.app/Contents/MacOS/Messages
che              1606   0.0  0.1  2495196   4628   ??  S    12:13PM   0:00.33 /usr/libexec/rtcreportingd
che              1542   0.0  0.2  2540248  17240   ??  S    11:40AM   0:00.32 /System/Library/PrivateFrameworks/CloudServices.framework/Resources/EscrowSecurityAlert.app/Contents/MacOS/EscrowSecurityAlert
che              1494   0.0  0.3  2511016  21696   ??  S    10:38AM   0:04.11 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
che              1493   0.0  0.4  2518780  31012   ??  S    10:38AM   0:04.53 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
che              1492   0.0  0.2  2510384  20604   ??  S    10:38AM   0:04.18 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
che              1486   0.0  0.3  2512068  22576   ??  S    10:36AM   0:04.07 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
che              1460   0.0  0.0  2494572   3944   ??  S    10:32AM   0:00.10 /System/Library/Frameworks/InputMethodKit.framework/Resources/imklaunchagent
_assetcache      1382   0.0  0.0  2469472   2316   ??  S    10:24AM   0:00.09 /System/Library/PrivateFrameworks/TCC.framework/Resources/tccd
_assetcache      1380   0.0  0.1  2499404   5576   ??  Ss   10:24AM   0:01.28 /System/Library/CoreServices/AssetCacheLocatorService
che              1251   0.0  0.1  2470592   6764   ??  S    10:24AM   0:00.12 /System/Library/CoreServices/mapspushd
che              1217   0.0  0.0  2469428   2440   ??  S    10:03AM   0:00.05 /System/Library/PrivateFrameworks/ToneLibrary.framework/Versions/A/XPCServices/com.apple.tonelibraryd.xpc/Contents/MacOS/com.apple.tonelibraryd
che              1077   0.0  0.2  2502588  19104   ??  S    Wed06AM   0:00.41 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/SpeechSynthesis.framework/Resources/com.apple.speech.speechsynthesisd
che              1050   0.0  0.3  2495488  21248   ??  S    Wed05AM   0:03.48 /System/Library/PrivateFrameworks/CoreRecents.framework/Versions/A/Support/recentsd
che              1041   0.0  0.1  2555584   7564   ??  S    Wed05AM   0:00.43 /System/Library/CoreServices/CoreServicesUIAgent.app/Contents/MacOS/CoreServicesUIAgent
che               997   0.0  0.0  2469424    968   ??  S    Wed12AM   0:00.15 /usr/libexec/USBAgent
che               978   0.0  0.0  2533240   3820   ??  S    Tue08PM   0:01.07 /System/Library/CoreServices/AirPlayUIAgent.app/Contents/MacOS/AirPlayUIAgent --launchd
che               905   0.0  0.1  2575604   8360   ??  Ss   Tue08PM   1:10.06 /System/Library/Frameworks/Foundation.framework/Versions/C/XPCServices/LookupViewService.xpc/Contents/MacOS/LookupViewService
che               794   0.0  0.0  2469404    788   ??  S    Tue08PM   0:00.04 /System/Library/PrivateFrameworks/KerberosHelper/Helpers/DiskUnmountWatcher
che               693   0.0  0.0  2471212   1020   ??  S    Tue08PM   0:00.20 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker-sizing -c MDSSizingWorker -m com.apple.mdworker.sizing
che               677   0.0  0.0  2504312   1268   ??  Ss   Tue08PM   0:03.64 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Frameworks/MediaConversionService.framework/Versions/A/XPCServices/com.apple.photos.ImageConversionService.xpc/Contents/MacOS/com.apple.photos.ImageConversionService
che               674   0.0  0.0  2493764    996   ??  Ss   Tue08PM   0:00.07 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.ComponentHelper.xpc/Contents/MacOS/com.apple.audio.ComponentHelper
che               673   0.0  0.0  2469456    944   ??  Ss   Tue08PM   0:00.04 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.SandboxHelper.xpc/Contents/MacOS/com.apple.audio.SandboxHelper
che               672   0.0  0.0   659548   1872   ??  Ss   Tue08PM   0:00.15 /System/Library/Frameworks/QTKit.framework/Versions/A/XPCServices/com.apple.qtkitserver.xpc/Contents/MacOS/com.apple.qtkitserver
che               667   0.0  0.0  2494976    872   ??  Ss   Tue08PM   0:00.08 /System/Library/PrivateFrameworks/SafariServices.framework/Versions/A/XPCServices/com.apple.SafariServices.xpc/Contents/MacOS/com.apple.SafariServices
che               664   0.0  0.0  2493764   1016   ??  Ss   Tue08PM   0:00.08 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.ComponentHelper.xpc/Contents/MacOS/com.apple.audio.ComponentHelper
che               663   0.0  0.0  2469456    936   ??  Ss   Tue08PM   0:00.06 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.SandboxHelper.xpc/Contents/MacOS/com.apple.audio.SandboxHelper
che               661   0.0  0.0  2508340   3404   ??  Ss   Tue08PM   0:02.69 /System/Library/PrivateFrameworks/PhotoLibrary.framework/Versions/A/XPCServices/com.apple.PhotoIngestService.xpc/Contents/MacOS/com.apple.PhotoIngestService
che               660   0.0  0.0  2500556   1420   ??  Ss   Tue08PM   0:00.08 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Frameworks/PhotoLibraryServices.framework/Versions/A/XPCServices/com.apple.photomoments.xpc/Contents/MacOS/com.apple.photomoments
che               659   0.0  0.3  2513736  25356   ??  S    Tue08PM   0:00.65 /System/Library/CoreServices/ScopedBookmarkAgent
che               656   0.0  0.0  2504104   2992   ??  Ss   Tue08PM   0:01.64 /System/Library/CoreServices/cloudphotosd.app/Contents/XPCServices/com.apple.ICPPhotoStreamLibraryService.xpc/Contents/MacOS/com.apple.ICPPhotoStreamLibraryService
che               654   0.0  0.1  2583512  10120   ??  S    Tue08PM   0:13.76 /System/Library/CoreServices/cloudphotosd.app/Contents/MacOS/cloudphotosd
che               621   0.0  0.0  2518752   1652   ??  Ss   Tue08PM   0:28.62 /System/Library/PrivateFrameworks/DiskImages.framework/Resources/diskimages-helper -uuid 0E450D04-2139-4138-BFEA-F498F0AF8D5D -post-exec 4
che               598   0.0  0.0  2493828   1520   ??  S    Tue08PM   0:11.94 /usr/libexec/SafariCloudHistoryPushAgent
che               590   0.0  0.0  2471188    156   ??  S    Tue08PM   0:00.18 /usr/libexec/SafariNotificationAgent
che               548   0.0  0.1  2500216   9684   ??  S    Tue08PM   0:00.23 /System/Library/PrivateFrameworks/DataDetectorsCore.framework/Versions/A/XPCServices/DataDetectorsDynamicData.xpc/Contents/MacOS/DataDetectorsDynamicData
che               512   0.0  0.0  2502492   2404   ??  Ss   Tue08PM   0:00.76 /System/Library/PrivateFrameworks/CloudDocsDaemon.framework/XPCServices/ContainerMetadataExtractor.xpc/Contents/MacOS/ContainerMetadataExtractor
che               495   0.0  0.1  3552656   7244   ??  S    Tue08PM   0:00.38 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storedownloadd
che               481   0.0  0.1  2542240   5484   ??  S    Tue08PM   0:00.36 /System/Library/PrivateFrameworks/CommerceKit.framework/Resources/LaterAgent.app/Contents/MacOS/LaterAgent
che               477   0.0  0.0  2516604   2004   ??  Ss   Tue08PM   0:00.13 /System/Library/Frameworks/AddressBook.framework/Versions/A/XPCServices/com.apple.AddressBook.InternetAccountsBridge.xpc/Contents/MacOS/com.apple.AddressBook.InternetAccountsBridge
che               475   0.0  0.1  2566124  10856   ??  S    Tue08PM   0:02.51 /System/Library/PrivateFrameworks/InternetAccounts.framework/Versions/A/XPCServices/com.apple.internetaccounts.xpc/Contents/MacOS/com.apple.internetaccounts
che               474   0.0  0.1  2501080   9480   ??  S    Tue08PM   0:01.48 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeassetd
che               473   0.0  0.0  2468920   1868   ??  S    Tue08PM   0:00.46 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storelegacy
che               461   0.0  0.0  2514464   3732   ??  S    Tue08PM   0:04.25 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Support/photolibraryd
che               447   0.0  0.1  2502240   8972   ??  Ss   Tue08PM   0:02.66 /System/Library/PrivateFrameworks/CalendarAgent.framework/Versions/A/XPCServices/CalNCService.xpc/Contents/MacOS/CalNCService
che               443   0.0  0.1  2528988   6488   ??  S    Tue08PM   0:00.78 /System/Library/Frameworks/InputMethodKit.framework/Versions/A/XPCServices/com.apple.InputMethodKit.UserDictionary.xpc/Contents/MacOS/com.apple.InputMethodKit.UserDictionary
che               442   0.0  0.0  2492928   1980   ??  S    Tue08PM   0:00.15 /System/Library/PrivateFrameworks/CommunicationsFilter.framework/CMFSyncAgent.app/Contents/MacOS/CMFSyncAgent
che               440   0.0  0.3  2599848  24412   ??  S    Tue08PM   0:04.59 /System/Library/Services/AppleSpell.service/Contents/MacOS/AppleSpell -psn_0_114716
che               432   0.0  0.1  2503668   7228   ??  S    Tue08PM   0:03.20 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistorySyncHelper
che               430   0.0  0.5  2571368  38052   ??  S    Tue08PM   0:22.65 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistoryPluginHelper
che               428   0.0  0.0  2468916    744   ??  Ss   Tue08PM   0:00.07 /System/Library/CoreServices/NotificationCenter.app/Contents/XPCServices/com.apple.notificationcenterui.WeatherSummary.xpc/Contents/MacOS/com.apple.notificationcenterui.WeatherSummary
che               427   0.0  0.0  2494900   2668   ??  Ss   Tue08PM   0:00.29 /System/Library/CoreServices/Menu Extras/AirPort.menu/Contents/XPCServices/com.apple.wifi.proxy.xpc/Contents/MacOS/com.apple.wifi.proxy
che               425   0.0  0.1  2544552   8048   ??  Ss   Tue08PM   0:01.41 /System/Library/CoreServices/Dock.app/Contents/XPCServices/com.apple.dock.extra.xpc/Contents/MacOS/com.apple.dock.extra
che               423   0.0  0.0  2496988   4132   ??  S    Tue08PM   0:07.30 /System/Library/CoreServices/lsuseractivityd
che               422   0.0  0.1  2496500   4272   ??  S    Tue08PM   0:00.82 /usr/libexec/fmfd
che               419   0.0  0.1  2498136   8096   ??  S    Tue08PM   0:01.06 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeaccountd
che               418   0.0  0.0  2497708   2608   ??  U    Tue08PM   0:00.33 /System/Library/CoreServices/pbs
che               415   0.0  0.1  2504460   9096   ??  S    Tue08PM   0:01.64 /System/Library/PrivateFrameworks/IMDPersistence.framework/XPCServices/IMDPersistenceAgent.xpc/Contents/MacOS/IMDPersistenceAgent
che               411   0.0  0.1  2554484  12552   ??  S    Tue08PM   0:02.66 /System/Library/PrivateFrameworks/ParsecUI.framework/Versions/A/Support/SpotlightNetHelper.app/Contents/MacOS/SpotlightNetHelper
che               410   0.0  0.1  2532360  11836   ??  S    Tue08PM   0:02.18 /System/Library/PrivateFrameworks/MessagesKit.framework/Resources/soagent.app/Contents/MacOS/soagent
che               407   0.0  0.0  2497540   4040   ??  S    Tue08PM   0:00.95 /System/Library/CoreServices/diagnostics_agent
che               406   0.0  0.0  2533780   3956   ??  S    Tue08PM   0:00.36 /System/Library/CoreServices/WiFiAgent.app/Contents/MacOS/WiFiAgent
che               403   0.0  0.0  2492996   2868   ??  S    Tue08PM   0:07.61 /System/Library/CoreServices/cloudpaird
che               402   0.0  0.1  2504208  10200   ??  S    Tue08PM   0:04.33 /System/Library/PrivateFrameworks/IMCore.framework/imagent.app/Contents/MacOS/imagent
che               401   0.0  0.0  2494012   1324   ??  S    Tue08PM   0:00.11 /System/Library/PrivateFrameworks/AskPermission.framework/Versions/A/Resources/askpermissiond
che               398   0.0  0.1  2496740   6788   ??  S    Tue08PM   0:06.24 /System/Library/CoreServices/AppleIDAuthAgent
che               397   0.0  0.4  2698660  30148   ??  S    Tue08PM   0:02.87 /System/Library/CoreServices/iconservicesagent
che               393   0.0  0.0  2542736   3720   ??  S    Tue08PM   0:00.33 /System/Library/CoreServices/Keychain Circle Notification.app/Contents/MacOS/Keychain Circle Notification
che               391   0.0  0.0  2494956   1708   ??  S    Tue08PM   0:00.13 /System/Library/CoreServices/SocialPushAgent.app/Contents/MacOS/SocialPushAgent
che               389   0.0  0.0  2469432    984   ??  S    Tue08PM   0:00.06 /usr/libexec/spindump_agent
che               388   0.0  0.1  2476896   5752   ??  S    Tue08PM   0:04.76 /usr/libexec/nsurlstoraged
che               387   0.0  0.4  2570144  30288   ??  S    Tue08PM   4:11.62 /System/Library/PrivateFrameworks/TelephonyUtilities.framework/callservicesd
che               384   0.0  0.1  2513708  11380   ??  S    Tue08PM   0:23.79 /System/Library/PrivateFrameworks/IDS.framework/identityservicesd.app/Contents/MacOS/identityservicesd
che               383   0.0  0.1  2497076   5148   ??  S    Tue08PM   0:01.23 /usr/libexec/pkd
che               381   0.0  0.2  2533572  20252   ??  S    Tue08PM   0:16.40 /usr/libexec/sharingd
che               380   0.0  0.1  2498048   8536   ??  S    Tue08PM   0:15.42 /usr/libexec/nsurlsessiond
che               379   0.0  0.2  2506380  13248   ??  S    Tue08PM   0:06.64 /System/Library/PrivateFrameworks/CloudDocsDaemon.framework/Versions/A/Support/bird
che               378   0.0  0.3  2518688  21800   ??  U    Tue08PM   0:38.39 /System/Library/PrivateFrameworks/CloudKitDaemon.framework/Support/cloudd
che               376   0.0  0.1  2531592   6988   ??  S    Tue08PM   0:13.26 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/ATS.framework/Support/fontd
che               374   0.0  0.2  3676612  15504   ??  S    Tue08PM   0:04.80 /System/Library/CoreServices/Spotlight.app/Contents/MacOS/Spotlight
che               373   0.0  0.1  2509748   7004   ??  S    Tue08PM   0:08.09 /System/Library/Frameworks/Accounts.framework/Versions/A/Support/accountsd
che               370   0.0  1.2  2825128 103968   ??  S    Tue08PM   0:41.26 /System/Library/CoreServices/Finder.app/Contents/MacOS/Finder
che               369   0.0  0.2  2570800  16264   ??  S    Tue08PM   0:12.49 /System/Library/CoreServices/SystemUIServer.app/Contents/MacOS/SystemUIServer
che               367   0.0  0.3  2714952  23820   ??  S    Tue08PM   0:44.07 /System/Library/CoreServices/Dock.app/Contents/MacOS/Dock
che               362   0.0  0.1  2502184   9732   ??  S    Tue08PM   0:36.23 /usr/libexec/secinitd
che               361   0.0  0.2  2537968  20312   ??  S    Tue08PM   0:31.79 /System/Library/PrivateFrameworks/CalendarAgent.framework/Executables/CalendarAgent
che               359   0.0  0.0  2495392   3984   ??  S    Tue08PM   0:02.02 /usr/sbin/usernoted
che               357   0.0  0.0  2468664    128   ??  S    Tue08PM   0:00.07 /usr/sbin/pboard
che               352   0.0  0.1  2496940   4932   ??  S    Tue08PM   0:12.63 /usr/libexec/UserEventAgent (Aqua)
che               316   0.0  0.0  2469216    420   ??  S    Tue08PM   0:00.97 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdflagwriter
che               292   0.0  0.0  2497856   2772   ??  S    Tue08PM   0:00.69 /System/Library/PrivateFrameworks/CloudServices.framework/Versions/A/XPCServices/com.apple.lakitu.xpc/Contents/MacOS/com.apple.lakitu
che               291   0.0  0.0  2494984   1580   ??  S    Tue08PM   0:00.21 /System/Library/PrivateFrameworks/CloudServices.framework/Resources/com.apple.sbd
che               279   0.0  0.0  2471100   1240   ??  S    Tue08PM   0:00.14 /System/Library/Frameworks/Security.framework/Versions/A/Resources/CloudKeychainProxy.bundle/Contents/MacOS/CloudKeychainProxy
che               278   0.0  0.0  2496448   2016   ??  S    Tue08PM   0:01.63 /usr/libexec/secd
che               277   0.0  0.1  2499248   5044   ??  U    Tue08PM   0:02.18 /System/Library/PrivateFrameworks/TCC.framework/Resources/tccd
che               274   0.0  0.0  2503092   3148   ??  S    Tue08PM   0:00.27 /System/Library/PrivateFrameworks/CloudPhotoServices.framework/Versions/A/Frameworks/CloudPhotoServicesConfiguration.framework/Versions/A/XPCServices/com.apple.CloudPhotosConfiguration.xpc/Contents/MacOS/com.apple.CloudPhotosConfiguration
che               272   0.0  0.1  2472836   5488   ??  S    Tue08PM   0:33.83 /usr/sbin/distnoted agent
che               266   0.0  0.0  2473752   3672   ??  S    Tue08PM   0:07.14 /usr/sbin/cfprefsd agent
che                83   0.0  0.3  2737716  27100   ??  Ss   Tue08PM   0:15.96 /System/Library/CoreServices/loginwindow.app/Contents/MacOS/loginwindow console
che              2446   0.0  0.0  2432772    640 s001  S+    8:46AM   0:00.00 grep che 
che              2442   0.0  0.0  2452828   1264 s001  S     8:45AM   0:00.01 -bash
