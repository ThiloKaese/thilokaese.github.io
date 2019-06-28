# PowerShell
## Install-Module fails
Trying to install docker-completion and failing with no module found or rather no repository present (Get-PSRepository returned empty)  
Also installing default PSGallery failed silently due to enterprise proxy settings

Found https://gist.github.com/guitarrapc/79d31b8cd02649075642b77c4ae796ab#gistcomment-2065520  
[system.net.webrequest]::defaultwebproxy = new-object system.net.webproxy('http://[YourProxyDNS]:[yourProxyPort]')  
[system.net.webrequest]::defaultwebproxy.credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials  
[system.net.webrequest]::defaultwebproxy.BypassProxyOnLocal = $true
