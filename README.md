# cloudcam-security-analysis
A security analysis of a manufacturer's Wi-Fi IP camera revealed an unauthenticated RTSP protocol and a default ONVIF configuration.

# OEM IP Camera Security Analysis
## Executive Summary
During a security assessment of a low-cost OEM Wi-Fi IP camera (“Cloud Cam”), security issues were identified.
The device exposes an unauthenticated RTSP stream on the local network, allowing any client to access live video without credentials.
Additionally, the ONVIF service is protected only by default credentials (admin:admin), which are accepted without enforcement of password change.

Using the ONVIF Media Service, it was possible to enumerate media profiles and retrieve a permanent RTSP URI that is not bound to a session, authentication, or timeout.
As a result, an attacker with network access can continuously monitor the camera feed without using the official mobile application.
These issues are common in OEM/ODM devices and may affect multiple rebranded products using the same firmware and hardware platform.

## Device Information
- Device type: OEM Wi-Fi IP Camera
- App name: Cloud Cam
- Firmware: 57.0.0.0629
- Services: RTSP, ONVIF, HTTP

  ## Attack Surface Discovery
