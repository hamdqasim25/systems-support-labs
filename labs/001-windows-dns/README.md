# 001 · Investigate a Windows DNS fault

**Status:** Planned  
**Environment:** Windows test VM with PowerShell and internet access  
**Scenario:** A user reports that a website will not load. A colleague suspects the network connection has dropped.

## Exercise

Use a disposable VM with a snapshot and local console access. The exercise changes the VM’s DNS settings temporarily. Record the active adapter’s current DNS configuration, including whether it is automatic or manual, before starting.

1. Establish a baseline. Run the checks below and confirm the hostname lookup and TCP connection succeed. If either fails, resolve the baseline issue before introducing the test fault.
2. In the test VM’s active adapter settings, set the IPv4 DNS server to the loopback address (127.0.0.1). This scenario assumes there is no DNS service listening there. Record any other configured resolvers that might still answer queries.
3. Run `Clear-DnsClientCache` in an elevated PowerShell window and repeat the checks. Compare the results. If name resolution still works, inspect which resolver answered and record what you found.
4. Restore the original DNS settings, clear the cache and repeat the same checks. Open https://example.com in the browser to verify the user’s task. Restore the snapshot if needed.

```powershell
Get-DnsClientServerAddress
Resolve-DnsName example.com -Type A -DnsOnly
Test-NetConnection 1.1.1.1 -Port 443
```

The TCP check uses a numeric address so it can test connectivity to that endpoint independently of the hostname lookup.

## Results to capture

| Stage | Hostname lookup | TCP connection | Evidence |
| --- | --- | --- | --- |
| Baseline | Pending | Pending | — |
| With test fault | Pending | Pending | — |
| After restoration | Pending | Pending | — |

## Ticket closure

After the run, add the observed symptom, the evidence that narrowed down the cause, the change that restored service and the browser retest result. Include one redacted before-and-after comparison.
