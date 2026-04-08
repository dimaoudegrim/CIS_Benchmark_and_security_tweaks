# CIS_Benchmark_and_security_registry_tweaks_for_home_users
Please check which settings are fit to your needs, few of these settings aren't oriented to organizations.
The settings are for Windows 11.
Disclaimer: I used Perplexity for summerize the titles or description in this readme.
________________________________________
🔒 Lock Screen
*	NoLockScreenCamera — Prevents the camera from being accessible on the lock screen
*	NoLockScreenSlideshow — Disables the lock screen slideshow
*	DisableLockScreenAppNotifications — Hides all app notifications on the lock screen
*	DontDisplayNetworkSelectionUI — Removes the network selector from the lock screen
*	BlockDomainPicturePassword — Prevents domain users from signing in with a picture password
*	LetAppsActivateWithVoiceAboveLock — Prevents apps from being activated by voice while the screen is locked
________________________________________
🌐 Network & SMB
*	EnableMulticast — Disables LLMNR multicast DNS name resolution
*	AllowInsecureGuestAuth — Blocks insecure guest authentication over SMB
*	RequireSecuritySignature (client & server) — Enforces SMB packet signing on both sides
*	RestrictAnonymous — Restricts anonymous access to network shares and named pipes
*	NTLMMinClientSec / NTLMMinServerSec — Requires NTLMv2 session security with 128-bit encryption
*	LmCompatibilityLevel — Forces NTLMv2 only; rejects LM and NTLMv1
*	RestrictSendingNTLMTraffic — Blocks outbound NTLM authentication to remote servers
*	UseMachineId — Uses the machine ID when authenticating via NTLM
*	DisableIPSourceRouting (IPv4 & IPv6) — Blocks IP source routing to prevent packet spoofing
*	NodeType — Sets NetBIOS name resolution to P-node (point-to-point, no broadcasts)
________________________________________
🖥️ Remote Desktop (RDP)
*	fDisableCcm — Disables COM port redirection in RDP sessions
*	fDisableCdm — Disables drive mapping redirection in RDP sessions
*	fDisableLocationRedir — Disables location redirection in RDP sessions
*	fDisableLPT — Disables LPT (printer) port redirection in RDP sessions
*	fDisablePNPRedir — Disables plug-and-play device redirection in RDP sessions
*	fPromptForPassword — Forces a password prompt when initiating an RDP connection
*	SecurityLayer — Sets RDP to use TLS (SSL) for transport security
*	AllowClipboardRedirection — Disables clipboard sharing between RDP client and host
*	DisablePasswordSaving — Prevents saving RDP passwords in the client
*	MaxDisconnectionTime — Sets a maximum session disconnection timeout
________________________________________
🛡️ Windows Defender & ASR
*	EnableNetworkProtection — Enables Defender Network Protection to block malicious domains
*	ExploitGuardASRRules — Enables Attack Surface Reduction (ASR) rules globally
*	ASR Rule GUIDs (multiple) — Each GUID enables a specific ASR rule, such as blocking Office macros spawning child processes, credential theft from LSASS, executable content from email, obfuscated scripts, etc.
*	PUAProtection — Enables blocking of Potentially Unwanted Applications
*	EnableFileHashComputation — Forces Defender to compute file hashes for threat intelligence
*	DisableGenericReports — Disables Defender sending generic sample reports to Microsoft
*	DisableEmailScanning (set to 0) — Keeps email scanning enabled in Defender
*	DisableRemovableDriveScanning (set to 0) — Keeps removable drive scanning enabled
________________________________________
⚙️ Virtualization-Based Security (VBS/HVCI)
*	EnableVirtualizationBasedSecurity — Turns on VBS to isolate critical system processes
*	RequirePlatformSecurityFeatures — Requires both Secure Boot and DMA protection for VBS
*	HypervisorEnforcedCodeIntegrity — Enables HVCI (Memory Integrity), protecting kernel code via hypervisor
________________________________________
🔑 Authentication & Accounts
*	FilterAdministratorToken — Enables UAC Admin Approval Mode for the built-in Administrator
*	EnhancedAntiSpoofing — Enables enhanced anti-spoofing for Windows Hello facial recognition
*	NoLocalPasswordResetQuestions — Disables security questions for local account password reset
*	BlockDomainPicturePassword — Prevents picture password login for domain accounts
*	NoGuest — Disables the built-in Guest account
*	CachedLogonsCount — Limits cached domain credential logons to 2
*	DisableDomainCreds — Prevents storing domain credentials in Windows Credential Manager
*	InactivityTimeoutSecs — Locks the screen after 900 seconds (15 minutes) of inactivity
*	DisableAutomaticRestartSignOn — Prevents automatic sign-in after a restart or update
*	UseEnhancedPin — Enables enhanced (alphanumeric) PIN for BitLocker
*	OSAllowSecureBootForIntegrity — Allows Secure Boot to be used for BitLocker integrity checks
________________________________________
🔐 LSA & Credential Protection
*	RunAsPPL — Runs the LSASS process as a Protected Process Light (PPL), preventing credential dumping
*	AllowDigest — Disables Digest authentication in WinRM (prevents cleartext credential exposure)
________________________________________
🖨️ Print Spooler
*	AddPrinterDrivers — Restricts adding printer drivers to administrators only
*	RegisterSpoolerRemoteRpcEndPoint — Disables the Print Spooler from accepting remote RPC connections (mitigates PrintNightmare)
*	DisableHTTPPrinting — Disables printing over HTTP
________________________________________
🔥 Windows Firewall
*	LogDroppedPackets (Domain, Private, Public) — Enables logging of dropped packets for all three firewall profiles
*	LogFileSize — Sets the maximum firewall log file size to 16,384 KB
________________________________________
💻 PowerShell
*	EnableScriptBlockLogging — Logs the content of all PowerShell script blocks executed
*	EnableModuleLogging — Logs all PowerShell module activity
*	EnableTranscripting — Disables PowerShell session transcription (kept off per CIS)
________________________________________
🌍 Privacy & Telemetry
*	AllowOnlineTips — Disables online tips and help suggestions from Microsoft
*	CEIP / CEIPEnable — Disables the Customer Experience Improvement Program
*	DoNotShowFeedbackNotifications — Suppresses Windows feedback prompts
*	DisableOneSettingsDownloads — Prevents Windows from downloading updated settings configs
*	EnableOneSettingsAuditing — Enables auditing of OneSettings policy changes
*	LimitDumpCollection — Restricts OS crash dump collection
*	LimitDiagnosticLogCollection — Limits diagnostic log data sent to Microsoft
*	Error Reporting Disabled — Disables Windows Error Reporting entirely
*	PreventHandwritingDataSharing — Stops handwriting input data from being shared with Microsoft
*	PreventHandwritingErrorReports — Prevents sending handwriting error reports to Microsoft
*	AllowInputPersonalization — Disables personalized input (typing/inking data collection)
________________________________________
📍 Location & Cortana
*	DisableLocation — Disables the Windows Location service
*	AllowCortana — Disables Cortana
*	AllowCortanaAboveLock — Disables Cortana from being usable on the lock screen
*	AllowSearchToUseLocation — Prevents Windows Search from using your location
________________________________________
📋 Clipboard & Sync
*	AllowCrossDeviceClipboard — Disables clipboard sharing across devices (Cloud Clipboard)
*	AllowMessageSync — Disables phone message syncing to the PC
*	UploadUserActivities — Disables uploading user activity history to Microsoft (Timeline)
*	EnableCdp — Disables the Connected Devices Platform (used for cross-device features)
________________________________________
🚗 AutoRun / AutoPlay
*	NoAutorun — Disables AutoRun for all drive types
*	NoDriveTypeAutoRun — Disables AutoPlay on all drive types (0xFF = all)
*	NoAutoplayfornonVolume — Disables AutoPlay for non-volume devices (e.g., cameras, phones)
________________________________________
🧩 Wireless & Bluetooth
*	DisableFlashConfigRegistrar — Disables Wi-Fi Protected Setup (WPS) via Flash
*	DisableInBand802DOT11Registrar — Disables in-band 802.11 WPS registrar
*	DisableUPnPRegistrar — Disables UPnP-based WPS registrar
*	DisableWPDRegistrar — Disables Windows Portable Devices WPS registrar
*	EnableRegistrars — Disables all wireless configuration registrars globally
*	DisableWcnUi — Disables the Windows Connect Now UI
*	AutoConnectAllowedOEM — Prevents auto-connecting to suggested open hotspots
*	RequirePinForPairing — Requires a PIN to pair new Bluetooth/wireless devices
________________________________________
🔧 Miscellaneous System Hardening
*	AllowRemoteShellAccess — Disables remote shell access via WinRM
*	SetDisablePauseUXAccess — Prevents users from pausing Windows Update
*	DisableEnclosureDownload — Disables automatic download of RSS feed enclosures
*	NoPublishingWizard — Disables the Web Publishing Wizard
*	NoOnlinePrintsWizard — Disables the online photo printing wizard
*	MSAOptional — Makes Microsoft Account sign-in optional for certain apps
*	AllowBuildPreview — Prevents enrollment in Windows Insider (preview) builds
*	EnableMSAppInstallerProtocol — Disables the ms-appinstaller URI protocol (exploited for malware delivery)
*	EnableHashOverride — Disables hash override in Windows Defender Application Control
*	EnableCertPaddingCheck — Enables WinVerifyTrust certificate padding validation (CVE-2013-3900 fix)
*	DisableExceptionChainValidation (set to 0) — Keeps SEHOP (Structured Exception Handler Overwrite Protection) enabled
*	AllowNewsAndInterests — Disables the News and Interests widget on the taskbar
*	AllowGameDVR — Disables Xbox Game DVR screen recording feature
*	AllowSuggestedAppsInWindowsInkWorkspace — Disables app suggestions in the Ink Workspace
*	SaveFilesToHost — Prevents Application Guard from saving files to the host
*	AllowNetworking (Application Guard) — Disables network access inside Application Guard sessions
*	AuditApplicationGuard — Enables audit logging for Application Guard events
*	HideRecommendedPersonalizedSites — Hides personalized/recommended sites in the Start menu
*	DisableCloudOptimizedContent — Disables cloud-fetched promotional content in Windows
*	PreventDeviceMetadataFromNetwork — Blocks Windows from fetching device metadata from the internet
*	DisableContentFileUpdates — Prevents offline maps from auto-updating
*	NotifyMalicious / NotifyUnsafeApp — Enables SmartScreen warnings for malicious sites and unsafe apps
*	AllowCloudSearch — Disables Bing cloud results in Windows Search
*	EnableExperimentalFeatures — Disables experimental WDAC policy features
*	Script Host Enabled (set to 0) — Disables Windows Script Host, blocking .vbs/.js script execution
*	fAllowToGetHelp — Disables Remote Assistance (offering or requesting help)
*	DontEnumerateConnectedUsers — Hides currently connected users from the logon screen
*	MSAOptional — Makes a Microsoft account non-mandatory for modern app sign-in
*	DisableRunAs — Disables the "Run as" option for published (RemoteApp) applications
*	W32Time Enabled — Ensures the Windows Time service runs for accurate time synchronization

