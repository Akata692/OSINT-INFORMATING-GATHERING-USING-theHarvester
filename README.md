# OSINT-INFORMATING-GATHERING-USING-theHarvester


## Objective

To practise Open-Source Intelligence (OSINT) information gathering using theHarvester in Kali Linux and understand how search engines and external data sources can be used to identify publicly available information associated with a domain.

## Tool Used

- **Tool:** theHarvester
- **Version shown:** 4.11.1
- **Operating system:** Kali Linux 2026.3
- **Environment:** Oracle VirtualBox
- **Target domain:** `microsoft.com`

## Commands Executed

### 1. Baidu Search

The following command was used to search for publicly available information associated with the target domain:

```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

Where:

- `-d` specifies the target domain.
- `-l` sets the maximum number of search results to retrieve.
- `-b` specifies the data source or search engine.

**Observed output:**

```text
Target: microsoft.com
Searching Baidu.

No IPs found.
No emails found.
No people found.
No hosts found.
```

The search completed but did not return any IP addresses, email addresses, people or hostnames.

### 2. Multiple-Source Search

A second command was executed to explore multiple available data sources:

```bash
theHarvester -d microsoft.com -l 50 -b all
```

The output showed that theHarvester attempted to process information from multiple sources.

However, several sources reported missing API keys or configuration requirements.

Examples visible in the terminal included:

- BeVigil
- Bitbucket
- BufferOverrun
- BuiltWith
- Brave Search
- Censys
- Criminal IP
- DeHashed

The tool displayed messages such as:

```text
Missing API key for bevigil.
Missing API key for Bitbucket.
Missing API key for bufferoverrun.
Missing API key for BuiltWith.
Missing API key for Brave Search.
Missing API key for Censys ID and/or Secret.
Missing API key for criminalip.
Missing API key for Dehashed.
```

These messages indicate that the relevant integrations could not be used without the required API credentials.

## Findings and Observations

| Area | Observation |
|---|---|
| Tool | theHarvester 4.11.1 |
| Target | `microsoft.com` |
| First search source | Baidu |
| First search limit | 1,000 |
| Second search source | All available sources requested |
| Second search limit | 50 |
| IP addresses | None returned by the Baidu search |
| Email addresses | None returned by the Baidu search |
| People | None returned by the Baidu search |
| Hosts | None returned by the Baidu search |
| API configuration | Several sources reported missing API keys |
| Command warning | The older `theharvester` command was reported as deprecated |

## Analysis

The exercise demonstrated how theHarvester can be used to collect publicly available information from different search engines and external data sources.

The Baidu search did not return any IP addresses, email addresses, people or hosts for the specified search. This does not establish that such information does not exist; it only describes the results returned by that particular search.

The broader search also demonstrated the importance of API configuration when working with OSINT tools. Some data sources require API keys or credentials before they can provide results.

The missing API-key messages limited the data sources available during the second attempt. Therefore, the output should not be interpreted as a complete search across all supported sources.

## Challenges and Solutions

### Challenge 1: Deprecated command warning

The initial command using `theharvester` displayed a warning that the command was deprecated and recommended using `theHarvester` instead.

**Solution:** I switched to the recommended command format:

```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```

This allowed me to proceed using the command shown in the tool's output.

### Challenge 2: Missing API keys

During the broader search, several data sources reported that their required API keys were missing.

**Solution:** I identified the affected integrations and documented the configuration limitation. The next step is to configure valid API credentials for the sources I am authorised to use, then repeat the search.

## Lessons Learned

- theHarvester supports OSINT information gathering from different search engines and data sources.
- Search results depend on the selected source and available information.
- A search returning no results does not prove that information does not exist.
- Some OSINT integrations require API keys before they can be used.
- Tool configuration can affect the completeness of an investigation.
- Deprecated commands should be replaced with the currently recommended syntax.
- Findings and technical limitations should be documented accurately.

## Evidence


<img width="2736" height="1824" alt="harvester2" src="https://github.com/user-attachments/assets/637ed9ca-612d-4de7-b7c4-74ed27a09e6e" />

01-theharvester-baidu-search

<img width="2736" height="1824" alt="harvester2 4" src="https://github.com/user-attachments/assets/6bccd498-9be7-421e-ac56-2f03ab03d239" />

02-theharvester-multiple-sources-api-keys.png



<img width="2736" height="1824" alt="harvester3" src="https://github.com/user-attachments/assets/1eee149b-df77-4ab6-b1c6-3a3383e3006e" />
03-theharvester-baidu-results.png


## Conclusion

This exercise provided practical experience using theHarvester 4.11.1 for OSINT information gathering in Kali Linux.

I performed a Baidu-based search and explored the use of multiple data sources. Although the first search returned no IP addresses, email addresses, people or hosts, the second attempt highlighted the importance of API credentials when integrating external information sources.

The exercise improved my understanding of OSINT workflows, command-line usage, data-source selection and troubleshooting tool configuration.

**Disclaimer:** This exercise is documented for educational purposes. The results reflect the supplied terminal output and do not represent a complete assessment of the target domain. Only conduct reconnaissance on domains and systems where you have appropriate authorisation.




# Author
Nicholas Gyemfi 

Cybersecurity Entusiast

LinkedIn: [https://www.linkedin.com/in/nic-gyim/](https://www.linkedin.com/in/nic-gyim/)
