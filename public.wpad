function FindProxyForURL(url, host)
{
 
  /* Normalize the URL for pattern matching */
      url = url.toLowerCase();
      host = host.toLowerCase();
  var hostIP = dnsResolve(host);
 
  /* Don't proxy local hostnames */
  if (isPlainHostName(host)) { return 'DIRECT'; }
 
  /* Don't proxy local domains */
  if (dnsDomainIs(host, ".dapla.net") || (host == "dapla.net") || dnsDomainIs(host, ".local") 
      || (host == "garterney.dapla.net") || dnsDomainIs(host, ".garterney.dapla.net")) {
      return 'DIRECT'; }
 
  if (isResolvable(host)) {
    /* Don't proxy non-routable addresses (RFC 3330) */
    if (isInNet(hostIP, '0.0.0.0', '255.0.0.0') ||
        isInNet(hostIP, '10.0.0.0', '255.0.0.0') ||
        isInNet(hostIP, '127.0.0.0', '255.0.0.0') ||
        isInNet(hostIP, '169.254.0.0', '255.255.0.0') ||
        isInNet(hostIP, '172.16.0.0', '255.240.0.0') ||
        isInNet(hostIP, '192.0.2.0', '255.255.255.0') ||
        isInNet(hostIP, '192.88.99.0', '255.255.255.0') ||
        isInNet(hostIP, '192.168.0.0', '255.255.0.0') ||
        isInNet(hostIP, '198.18.0.0', '255.254.0.0') ||
        isInNet(hostIP, '224.0.0.0', '240.0.0.0') ||
        isInNet(hostIP, '240.0.0.0', '240.0.0.0')) {
        return 'DIRECT';}
 
    /* Don't proxy local addresses.*/
    if (false) { return 'DIRECT'; }
  }
  
  /* actual proxy settings */
  return 'DIRECT';
}
