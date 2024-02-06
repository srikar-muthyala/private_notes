## Using SSRF to scan for internal network assets

Server-Side Request Forgery vulnerabilities abuse the lack of input validation on user-supplied URLs while fetching remote resources

Most of the time, the fetching URL can be replaced with an internal IP or hostname (i.e: "localhost") to verify the existence of the resource

Once you found the running services, you can use an Out-of-Band technique to read the output (works well for Jira, Confluence, Jenkins, Weblogic, and many other)

**Example**

1. Find a feature that connects to an external service or fetches data from an URL
2. Intercept the request and replace the host with an internal address ("localhost" or "127 0 0 1")
3. Run Intruder against each port of the target host
4. Compare results to determine successful/failed connections
5. Map the ports to services and use Out-of-Band techniques if no output is returned (Blind SSRF)

**5000 ports wordlist for intruder -** https://raw.githubusercontent.com/HeckerBirb/top-nmap-ports-csv/master/top-5000-most-popular-tcp-ports-nmap-sorted.csv
