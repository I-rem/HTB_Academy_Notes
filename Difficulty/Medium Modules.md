# Brief Intro to Hardware Attacks
## Bluetooth Attacks
`Bluetooth`, a wireless technology standard The technology operates by establishing `personal area networks` (PANs) using `radio frequencies` in the `ISM band from 2.402 GHz to 2.480 GHz`. Conceived as a `wireless alternative to RS-232 data cables`,

After pairing, Bluetooth devices form a network known as a `piconet`. This collection of devices connected via Bluetooth technology consists of one `main` device and up to seven `active client` devices. The `main` device coordinates communication within the piconet.

Multiple piconets can interact to form a larger network known as a `scatternet`. In this configuration, some devices serve as bridges,

The Bluetooth specification identifies two types of links for data transfer:

1.  `Synchronous Connection-Oriented (SCO) links`: Primarily used for audio communication these links reserve slots at regular intervals for data transmission, guaranteeing steady, uninterrupted communication
2. `Asynchronous Connection-Less (ACL) links`: These links cater to transmitting all other types of data. Unlike SCO links, ACL links do not reserve slots but transmit data whenever bandwidth allows.

Bluejacking

Bluejacking is a relatively harmless type of Bluetooth hacking where an attacker `sends unsolicited messages` or business cards to a device. Although it doesn't pose a direct threat, it can infringe on privacy and be a nuisance to the device owner.

Bluesnarfing

Bluesnarfing entails `unauthorised access to a Bluetooth-enabled device's data`, such as contacts, messages, or calendar entries. Attackers exploit vulnerabilities to retrieve sensitive information without the device owner's knowledge or consent. This could lead to privacy violations and potential misuse of personal data.

Bluebugging

Bluebugging enables an attacker to `control a Bluetooth device`, including making calls, sending messages, and accessing data. By exploiting security weaknesses, attackers can gain unauthorised access and manipulate the device's functionalities, posing a significant risk to user privacy and device security.

Car Whisperer

Car Whisperer is a Bluetooth hack that `specifically targets vehicles`. Attackers exploit Bluetooth vulnerabilities to remotely unlock car doors or even start the engine without physical access. This poses a serious security threat as it can lead to car theft and compromise the safety of vehicle owners.

Bluesmacking & Denial of Service

Denial of Service (DoS) attacks leverage vulnerabilities in Bluetooth protocols to `disrupt or disable the connection between devices`. Bluesmacking, a specific type of DoS attack, involves sending excessive Bluetooth connection requests, overwhelming the target device and rendering it unusable. These attacks can disrupt normal device operations and cause inconvenience to users.

Man-in-the-Middle

Man-in-the-Middle (MitM) attacks intercept and manipulate data exchanged between Bluetooth devices. By `positioning themselves between the communicating devices`, attackers can eavesdrop on sensitive information or alter the transmitted data. MitM attacks compromise the confidentiality and integrity of Bluetooth communications, posing a significant risk to data security.

BlueBorne

Discovered in 2017, BlueBorne is a critical Bluetooth vulnerability that allows an attacker to take `control of a device without requiring any user interaction or device pairing`. Exploiting multiple zero-day vulnerabilities, BlueBorne presents a severe threat to device security and user privacy. Its pervasive nature makes it a significant concern across numerous Bluetooth-enabled devices.

Key Extraction

Key extraction attacks aim to `retrieve encryption keys` used in Bluetooth connections. By obtaining these keys, attackers can decrypt and access sensitive data transmitted between devices. Key extraction attacks undermine the confidentiality of Bluetooth communications and can result in exposure of sensitive information.

Eavesdropping

Eavesdropping attacks involve `intercepting and listening to Bluetooth communications`. Attackers capture and analyse data transmitted between devices, potentially gaining sensitive information such as passwords, financial details, or personal conversations. Eavesdropping attacks compromise the confidentiality of Bluetooth communications and can lead to severe privacy violations.

Bluetooth Impersonation Attack

In this attack type, an attacker `impersonates a trusted Bluetooth device` to gain unauthorised access or deceive the user. By exploiting security vulnerabilities, attackers can trick users into connecting to a malicious device, resulting in data theft, unauthorised access, or other malicious activities. Bluetooth impersonation attacks undermine trust and integrity in Bluetooth connections, posing a significant risk to device security and user trust.


[Bluetooth Special Interest Group (Bluetooth SIG)](https://en.wikipedia.org/wiki/Bluetooth_Special_Interest_Group)
## Modern Bluetooth Attacks and Mitigation

### KNOB

The `Key Negotiation of Bluetooth (KNOB)` attack exploits a flaw in the Bluetooth standard to `undermine the encryption` of Bluetooth connections.

The attacker intercepts the Bluetooth pairing communication and `forcibly sets the length` of the encryption key to its `minimum allowed size`, which is only `one byte`. With such a weak encryption key, it becomes trivial for the attacker to crack it through `brute force` methods, thereby gaining access to the encrypted communication.

### BIAS

`Bluetooth Impersonation AttackS (BIAS)` enables the attacker to `authenticate themselves` by connecting with a victim's device and `masquerading` as a `device already paired` with the victim's.

### Mitigation
Keep Devices Updated
Disable Bluetooth When Not Needed
Enable Device Pairing Authorisation
Limit Device Visibility
Exercise Caution in Public Settings

## Crypto Analysis
[Scytale](https://en.wikipedia.org/wiki/Scytale)
However, the `first recorded instance` of Cryptanalysis came from the `Arabic scientist Al-Kindi`  He wrote a book on decrypting encrypted code, introducing the `first recorded frequency analysis method`.

During the Renaissance, The Italian scholar Giovanni Battista della Porta wrote "`De Furtivis Literarum Notis`", aka "`On the Hidden Notes of Letters`", a pioneering collection of work on the subject.

World War II, in particular, witnessed massive strides in cryptanalysis with the breaking of the `German Enigma machine` cypher at Bletchley Park. This achievement, led by British cryptanalyst `Alan Turing` and his team

## Side-Channel Attacks
2 Types
`Passive Side-Channel Attacks`: the attacker monitors the system without actively interfering.  This could include observing aspects such as power consumption, timing, or electromagnetic emissions.

`Active Side-Channel Attacks`: The attacker deliberately manipulates the system to provoke informative alterations. This could involve manipulating the system's power supply or introducing particular inputs to observe output or operation time changes.

### Timing Attacks
the attacker measures the `computation time` of cryptographic algorithms and `makes informed guesses` about the secret key based on the `observed variations`.

Mitigation of timing attacks often involves the use of `constant-time` algorithms.
### Power-Monitoring Attacks
`Simple Power Analysis (SPA)`: the attacker directly interprets the power consumption graph to identify operations. For instance, a spike in power use could indicate a specific operation, revealing a bit of the secret key.

`Differential Power Analysis (DPA)`: his method is more sophisticated and involves collecting power consumption data for many operations and using statistical analysis to find correlations between power consumption and the values of bits in the secret key.
### Acoustic Cryptoanalysis
`extract sensitive information from a system by analysing the sound emissions` it produces during its operation.
sound produced by a computer's CPU, fans, and other components can change based on the computations it's performing
https://github.com/ggerganov/kbd-audio

## Microprocessor Optimization Strategies
### Pipelining
### Speculative Execution
`making educated guesses` about the potential direction a program might take, particularly when faced with a conditional branch instruction

Instead of waiting to determine the correct path (which can cause delays), the microprocessor will predict the most likely path and execute instructions along that pathway

this method requires an efficient rollback mechanism. If the prediction is incorrect, the microprocessor must discard the speculatively executed instructions, revert to its pre-speculation state, and resume along the correct path.
### Caching
 microprocessors use caches, which are `small`, `high-speed memory units` placed between the CPU and the main memory. They store `frequently or recently accessed data`
Caches are usually organised in a hierarchy of levels (`L1`, `L2`, `L3`), with `L1` being the smallest and fastest and directly interfacing with the CPU, while the `lower levels are larger and slower`
## Microprocessor Vulnerabilities
infamous example of a side-channel attack is the `Spectre` and `Meltdown` vulnerabilities discovered in 2018.

`Spectre` `breaks the isolation between different applications`, takes advantage of the `speculative execution` technique used in modern microprocessors. If the predictions are wrong, the instructions and their direct effects are discarded to maintain program correctness  Despite discarding the direct effects of incorrect speculative execution, subtle, indirect effects may persist, particularly in micro-architectural structures like the `cache`.

The `Spectre` vulnerability intentionally causes the processor to make incorrect predictions which initiate the speculative execution of a specially chosen set of instructions.

 Meltdown dissolves the more fundamental `isolation between user applications and the operating system`. This allows a malicious program to access the memory of other programs and the operating system, exploitation of a feature of modern microprocessors known as `out-of-order execution`.
 
. It begins by inducing an exception — for example, by attempting to access a privileged memory location that is off-limits to user programs. While handling this exception would usually involve discarding the effects of the offending instruction, the out-of-order execution allows further instructions that depend on this illegal access to be executed before the exception is handled.
undermines kernel/user space isolation
## Mitigation strategies
### Retpoline
An `indirect software branch` refers to a type of program instruction that guides the execution path based on specific conditions. Unlike a `direct branch`, where the destination is pre-determined and known in advance, the destination of an indirect branch is determined dynamically during runtime.

The fundamental idea behind `retpoline` is to modify the control flow so that `speculative execution is avoided` when encountering indirect branches.

However, `retpolines` may impose a performance overhead, particularly in applications with many indirect branches.
### Compiler Barriers
`Memory Barriers` (or `Fence Instructions`) ensure that all load and store memory operations before the barrier are completed before any operations that come after the barrier.

`Branch Prediction Barriers` are used to inhibit speculative execution at certain points in the code where it could lead to a security vulnerability.

### KPTI
primary mitigation technique against `Meltdown`

# DNS Enumeration Using Python
zone files are lists of entries for the corresponding domain. We can think of it like a telephone book for a specific city. These zone files contain `IP addresses` to the specific `domains` and `hosts`.

Each domain consists of at least two parts:

1.  `Top-Level Domain` (`TLD`)
2.  `Domain Name`
The DNS servers are divided into four different types:

-   `Recursive resolvers` (`DNS Recursor`)
-   `Root name server`
-   `TLD name server`
-   `Authoritative name servers`

## Recursive DNS Resolver

The recursive resolver acts as an agent between the client and the name server. After the recursive resolver receives a DNS query from a web client, it responds to this query with cached data, or it sends a query to a root name server, followed by a query to a TLD name server and finally a final query to an authoritative name server. Once it has received a response from the authoritative name server with the requested IP address, the recursive resolver sends the client's response.

During this process, the recursive resolver stores the received information from authoritative name servers in its cache. When a client requests the IP address of a domain name that was recently requested by another client, the resolver can skip communication with the name servers and retrieve the requested entry from its cache and send it to the client.

## Programming Guidelines
There are guidelines developed especially for Python, known as the `Python Enhancement Proposal` (`PEP8`). [PEP8](https://www.python.org/dev/peps/pep-0008/)

Indentation: 4 spaces, no tabs!

Max. Line Length for Code: 79 characters / line

Max. Line Length for Comments/DocStrings: 72 characters / line

Encoding: UTF-8 for Python 3

Quotes: The use of single and double quotes is possible, but we should decide on one of them.

## DNS Zones
### Primary DNS Server

The primary DNS server is the server of the zone file, which contains all authoritative information for a domain and is responsible for administering this zone.
### Secondary DNS Server
contain read-only copies of the zone file from the primary DNS server. These servers compare their data with the primary DNS server at regular intervals and thus serve as a backup server.
### Zone Files
we distinguish between:

-   `Primary zone` (`master zone`)
-   `Secondary zone` (`slave zone`)

The `secondary zone` on the secondary DNS server serves as a substitute for the `primary zone` on the primary DNS server if the primary DNS server should become unreachable

The creation and transfer of the `primary zone` copy from the primary DNS server to the secondary DNS server is called a "`zone transfer`."

Each zone file can have only one primary DNS server and an unlimited number of secondary DNS servers.

### Zone transfer
There are two different types of zone transfers.

-   `AXFR` - Asynchronous Full Transfer Zone: An `AXFR` is a complete transfer of all entries of the zone file
-   `IXFR` - Incremental Zone Transfer: only the changed and new DNS records of the zone file are transferred for an `IXFR` to the secondary DNS servers.

The problem with DNS servers and zone transfers is that it does not require authentication and can be requested by any client. If the administrator has not set "Trusted Hosts/IP addresses" for the DNS servers,
## DNS Reocrds and Queries
DNS records are instructions that are located on authoritative DNS servers and contain information about a domain.
A	IP Version 4 Address records
AAAA	IP Version 6 Address records
CNAME	Canonical Name records
HINFO	Host Information records
ISDN	Integrated Services Digital Network records
MX	Mail exchanger record
NS	Name Server records
PTR	Reverse-lookup Pointer records
SOA	Start of Authority records
TXT	Text records

There are many tools and resources we can work with to send queries to the DNS servers like : **dig** and **nslookup**

## Performing DNS Zone Transfer
```shell-session
dig axfr inlanefreight.com @10.129.2.67
```