
# Awesome Security Tools [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated collection of security tools, resources, and frameworks for security professionals, developers, and DevSecOps teams. This list focuses on practical, production-ready tools with detailed descriptions and real-world use cases.

**Mission**: Help security teams discover, evaluate, and implement security tools that actually work in production environments.

---

## Contents

- [Network Security](#network-security)
- [Web Application Security](#web-application-security)
- [Cloud Security](#cloud-security)
- [Container & Kubernetes Security](#container--kubernetes-security)
- [Static Application Security Testing (SAST)](#static-application-security-testing-sast)
- [Dynamic Application Security Testing (DAST)](#dynamic-application-security-testing-dast)
- [Software Composition Analysis (SCA)](#software-composition-analysis-sca)
- [Secrets Management & Detection](#secrets-management--detection)
- [Penetration Testing](#penetration-testing)
- [Vulnerability Management](#vulnerability-management)
- [Security Automation & Orchestration](#security-automation--orchestration)
- [Compliance & Auditing](#compliance--auditing)
- [Incident Response & Forensics](#incident-response--forensics)
- [Threat Intelligence](#threat-intelligence)
- [Security Monitoring & SIEM](#security-monitoring--siem)
- [API Security](#api-security)
- [Mobile Security](#mobile-security)
- [Database Security](#database-security)
- [Identity & Access Management](#identity--access-management)
- [Cryptography & PKI](#cryptography--pki)
- [Security Training & CTF](#security-training--ctf)
- [Security Frameworks & Standards](#security-frameworks--standards)

---

## Network Security

### Network Scanning & Discovery

- **[Nmap](https://nmap.org/)** - Industry-standard network scanner for host discovery, port scanning, OS detection, and service enumeration. Essential for network reconnaissance and asset inventory. Includes powerful NSE (Nmap Scripting Engine) for vulnerability detection, backdoor discovery, and advanced network exploration. Supports IPv6, SSL/TLS scanning, and custom protocol detection.

- **[Masscan](https://github.com/robertdavidgraham/masscan)** - World's fastest Internet port scanner capable of scanning the entire Internet in under 6 minutes at 10 million packets per second. Ideal for large-scale network reconnaissance, internet-wide studies, and attack surface discovery. Uses custom TCP/IP stack for maximum speed. Perfect for pentesters and security researchers needing fast network enumeration.

- **[RustScan](https://github.com/RustScan/RustScan)** - Modern port scanner written in Rust that turns a 17-minute Nmap scan into 19 seconds. Automatically pipes results to Nmap for service detection. Features adaptive timing, CIDR support, and custom scripts. Great for bug bounty hunters and pentesters who need speed without sacrificing Nmap's powerful features.

- **[Nuclei](https://github.com/projectdiscovery/nuclei)** - Fast and customizable vulnerability scanner based on YAML templates. Includes 3,000+ community templates for CVE detection, misconfigurations, and security flaws. Used by security teams for continuous vulnerability assessment, bug bounty automation, and compliance scanning. Supports custom workflows, headless browser automation, and multi-step scanning logic.

- **[Shodan](https://www.shodan.io/)** - Search engine for Internet-connected devices (IoT, ICS/SCADA, servers, webcams). Essential for attack surface discovery, threat intelligence, and identifying exposed assets. API available for automated scanning. Used by red teams to find vulnerable entry points and blue teams to discover shadow IT.

### Intrusion Detection & Prevention

- **[Suricata](https://suricata.io/)** - High-performance Network IDS/IPS and security monitoring engine. Supports multi-threading, hardware acceleration, and complex protocol analysis. Includes signature-based detection (Snort-compatible), anomaly detection, and file extraction. Perfect for SOC environments needing real-time threat detection at 10Gbps+ speeds. Integrates with ELK Stack, Splunk, and major SIEM platforms.

- **[Snort](https://www.snort.org/)** - Original open-source IDS/IPS with 20+ years of development. Features rule-based detection with 300,000+ community rules, protocol analysis, and content matching. Widely deployed in enterprises and praised for stability. Snort 3 introduces multi-threading and better performance. Essential for compliance (PCI-DSS) and network security monitoring.

- **[Zeek (formerly Bro)](https://zeek.org/)** - Network security monitor that provides high-level network analysis and security monitoring. Goes beyond signature matching to provide detailed logs of network activity, protocol analysis, and behavioral analytics. Excellent for threat hunting, incident response, and forensic analysis. Extensible via custom scripts. Used by NSA, major universities, and Fortune 500 companies.

- **[OSSEC](https://www.ossec.net/)** - Host-based intrusion detection system (HIDS) that performs log analysis, file integrity checking, rootkit detection, and real-time alerting. Multi-platform support (Linux, Windows, macOS). Centralized management for thousands of agents. Great for compliance (PCI-DSS, HIPAA) and insider threat detection. Active community with 1,000+ pre-built rules.

- **[Wazuh](https://wazuh.com/)** - Open-source security platform that unifies SIEM and XDR capabilities. Built on OSSEC with enhanced features: log analysis, intrusion detection, vulnerability detection, configuration assessment, incident response, and compliance monitoring. Includes beautiful dashboards, threat intelligence integration, and cloud security posture management. Scales to 100,000+ agents.

### Network Traffic Analysis

- **[Wireshark](https://www.wireshark.org/)** - World's most popular network protocol analyzer. Deep inspection of 2,000+ protocols with live capture and offline analysis. Essential for troubleshooting, security analysis, and protocol development. Features powerful display filters, export options, and VoIP analysis. GUI and command-line (tshark) interfaces available. Every security professional's toolkit essential.

- **[tcpdump](https://www.tcpdump.org/)** - Command-line packet analyzer for network troubleshooting and security analysis. Lightweight, fast, and available on every Unix system. Perfect for remote packet capture, automated analysis, and headless servers. Outputs pcap format compatible with Wireshark. Essential for DevOps and SRE teams investigating network issues.

- **[NetworkMiner](https://www.netresec.com/?page=NetworkMiner)** - Network forensic analysis tool that extracts artifacts from PCAP files: files, images, emails, credentials, sessions. Doesn't require packet injection, operates passively. Excellent for incident response, malware analysis, and digital forensics. Reconstructs TCP sessions and identifies operating systems/applications without sending packets.

### Firewall & Network Security

- **[pfSense](https://www.pfsense.org/)** - Open-source firewall and router based on FreeBSD. Enterprise-grade features: VLAN support, VPN (OpenVPN, IPsec, WireGuard), traffic shaping, load balancing, and high availability. Web-based management interface with 300+ packages available. Powers networks from small businesses to ISPs. Excellent Netgate hardware appliances available.

- **[OPNsense](https://opnsense.org/)** - Fork of pfSense with more frequent updates and modern UI. Includes built-in IDS/IPS (Suricata), web filtering, and extensive plugin ecosystem. Easy to use yet powerful enough for enterprise deployments. Active development community and commercial support available. Great choice for those wanting latest features and security patches.

### VPN & Tunneling

- **[WireGuard](https://www.wireguard.com/)** - Modern VPN protocol that's faster, simpler, and more secure than IPsec and OpenVPN. Uses state-of-the-art cryptography (Curve25519, ChaCha20, Poly1305). Minimal attack surface with only 4,000 lines of code. Built into Linux kernel 5.6+. Ideal for cloud connectivity, site-to-site VPNs, and remote access. Significantly faster than alternatives with lower latency.

- **[OpenVPN](https://openvpn.net/)** - Mature open-source VPN solution with SSL/TLS security. Highly configurable with support for various authentication methods, compression, and networking modes. Widely deployed in enterprises for 15+ years. Strong community support and extensive documentation. Available on all platforms including mobile. Great for traditional VPN deployments.

- **[Tailscale](https://tailscale.com/)** - Modern VPN built on WireGuard that creates secure mesh networks between devices. Zero-configuration with automatic NAT traversal and key management. Integrates with SSO providers (Google, Okta, Azure AD). Perfect for remote teams, development environments, and secure access to internal resources. Free tier available for personal use.

---

## Web Application Security

### Web Vulnerability Scanners

- **[OWASP ZAP (Zed Attack Proxy)](https://www.zaproxy.org/)** - World's most popular open-source web application security scanner. Intercepts HTTP/HTTPS traffic, performs automated and manual testing for OWASP Top 10 vulnerabilities. Features: active/passive scanning, fuzzing, API testing, and authentication support. Includes powerful scripting engine and marketplace with 100+ add-ons. Essential for DevSecOps pipelines and penetration testing. Used by 20,000+ organizations worldwide.

- **[Burp Suite Community Edition](https://portswigger.net/burp/communitydownload)** - Industry-standard toolkit for web security testing. Features intercepting proxy, scanner (Pro only), repeater, intruder, and decoder. Extensible via BApps with 400+ plugins. Professional version includes advanced scanner, automation, and collaboration features. Every web security professional's primary tool. Free community edition great for learning.

- **[Nikto](https://github.com/sullo/nikto)** - Open-source web server scanner that tests for 6,800+ dangerous files, outdated software versions, and server misconfigurations. Fast and lightweight, perfect for quick security assessments. Identifies common vulnerabilities like default credentials, exposed admin panels, and security headers issues. Integrates well with Metasploit and CI/CD pipelines.

- **[Arachni](https://www.arachni-scanner.com/)** - Feature-rich web application security scanner with high performance and accuracy. Supports complex web apps with JavaScript, REST APIs, and AJAX. Features browser environment emulation, multiple scan types (direct, proxy, reverse proxy), and extensive reporting. Command-line and web UI available. Great for automated security testing in development.

- **[Wapiti](https://wapiti-scanner.github.io/)** - Black-box web vulnerability scanner that audits web applications by crawling and injecting payloads. Detects SQL injection, XSS, XXE, SSRF, and 25+ vulnerability types. Generates reports in HTML, JSON, XML. Lightweight Python tool perfect for CI/CD integration. Supports authentication and complex scanning scenarios.

### Web Application Firewalls (WAF)

- **[ModSecurity](https://modsecurity.org/)** - Open-source WAF engine that works with Apache, Nginx, and IIS. Provides rule-based filtering, virtual patching, and real-time monitoring. Core Rule Set (CRS) protects against OWASP Top 10 with 200+ rules. Used by CloudFlare, Akamai, and millions of websites. Extremely flexible with custom rule creation. Essential for protecting legacy applications that can't be patched.

- **[NAXSI](https://github.com/nbs-system/naxsi)** - Open-source WAF for Nginx that uses whitelist approach instead of signatures. Low false-positive rate and high performance. Learning mode automatically generates whitelists from legitimate traffic. Perfect for protecting APIs and modern web applications. Minimal configuration required. Great alternative to ModSecurity for Nginx users.

- **[Shadow Daemon](https://shadowd.zecure.org/)** - Collection of tools to detect, record, and prevent attacks on web applications. Uses whitelist learning mode and anomaly detection. Protects against SQL injection, XSS, path traversal, and more. Includes web interface for rule management and attack visualization. Lightweight with minimal performance impact.

### API Security

- **[Postman](https://www.postman.com/)** - Popular API development and testing platform with security testing capabilities. Features automated testing, environment management, and collaboration. Can detect common API vulnerabilities like broken authentication, excessive data exposure, and injection flaws. Includes mock servers and API monitoring. 20M+ developers use Postman for API security testing.

- **[OWASP API Security Top 10](https://owasp.org/www-project-api-security/)** - Critical security risks for APIs including broken authentication, excessive data exposure, lack of rate limiting, and security misconfigurations. Essential reading for API developers and security teams. Includes testing guides and mitigation strategies.

- **[Insomnia](https://insomnia.rest/)** - Open-source API client with GraphQL and REST support. Features environment variables, code generation, and authentication flows. Great for API security testing with scripting capabilities. Cleaner interface than Postman. Perfect for developers doing security testing.

### SSL/TLS Testing

- **[SSLyze](https://github.com/nabla-c0d3/sslyze)** - Fast and comprehensive SSL/TLS scanner written in Python. Tests cipher suites, certificate validation, TLS compression, session resumption, and more. Identifies weak configurations, expired certificates, and protocol vulnerabilities. JSON output perfect for CI/CD integration. Used by security teams for continuous SSL monitoring.

- **[testssl.sh](https://testssl.sh/)** - Command-line tool that checks SSL/TLS configurations on any port. Tests for protocol support, cipher strength, certificate validity, and 40+ vulnerabilities (POODLE, BEAST, CRIME, Heartbleed). Color-coded output makes results easy to understand. Doesn't require OpenSSL installation. Essential for compliance and security audits.

- **[SSL Labs](https://www.ssllabs.com/ssltest/)** - Online service by Qualys that grades SSL/TLS configurations (A+ to F). Tests certificates, protocol support, cipher strength, and vulnerabilities. Provides detailed explanations and remediation advice. Industry-standard for SSL testing. API available for automated testing.

---

## Cloud Security

### Multi-Cloud Security Posture Management

- **[Prowler](https://github.com/prowler-cloud/prowler)** - Open-source cloud security tool for AWS, Azure, GCP, and Kubernetes. Performs 300+ security checks across CIS Benchmarks, PCI-DSS, GDPR, HIPAA, and more. Identifies misconfigurations, compliance violations, and security gaps. Generates detailed reports in HTML, JSON, CSV. Integrates with security orchestration platforms. Essential for cloud security audits and continuous compliance monitoring.

- **[ScoutSuite](https://github.com/nccgroup/ScoutSuite)** - Multi-cloud security auditing tool supporting AWS, Azure, GCP, Alibaba Cloud, and Oracle Cloud. Gathers configuration data via APIs and presents security posture through interactive HTML reports. Identifies attack paths, excessive permissions, and misconfigurations. No agents required, runs entirely via cloud APIs. Great for initial security assessments.

- **[CloudSploit](https://github.com/aquasecurity/cloudsploit)** - AWS security scanning tool with 100+ plugins checking for common misconfigurations and security risks. Tests IAM policies, S3 bucket permissions, security groups, encryption, logging, and more. Fast, lightweight, and easy to integrate into CI/CD. Acquired by Aqua Security and actively maintained.

- **[Checkov](https://www.checkov.io/)** - Static analysis tool for infrastructure-as-code (Terraform, CloudFormation, Kubernetes, ARM templates, Helm). Detects misconfigurations before deployment with 1,000+ built-in policies. Prevents security issues at code level following "shift-left" approach. Integrates with CI/CD pipelines. Supports custom policies in Python or YAML. Essential for DevSecOps teams.

### AWS Security

- **[AWS Security Hub](https://aws.amazon.com/security-hub/)** - Centralized security and compliance dashboard for AWS accounts. Aggregates findings from GuardDuty, Inspector, Macie, IAM Access Analyzer, and 60+ partner solutions. Automated compliance checks against CIS, PCI-DSS, and AWS best practices. Provides security score and prioritized findings. Native AWS service with no agents required.

- **[AWS GuardDuty](https://aws.amazon.com/guardduty/)** - Intelligent threat detection service that monitors for malicious activity and unauthorized behavior. Analyzes VPC Flow Logs, CloudTrail logs, and DNS queries using machine learning. Detects cryptocurrency mining, credential compromise, and reconnaissance. Low false-positive rate with actionable findings. Pricing based on volume of analyzed events.

- **[CloudMapper](https://github.com/duo-labs/cloudmapper)** - Open-source tool for visualizing AWS environments and identifying security issues. Generates network diagrams, identifies publicly accessible resources, and checks IAM policies. Great for understanding complex AWS architectures and attack surfaces. Produces beautiful SVG diagrams showing VPCs, subnets, and security groups.

- **[PMapper](https://github.com/nccgroup/PMapper)** - Principal Mapper analyzes AWS IAM permissions to identify privilege escalation risks. Maps out what each principal (user/role) can do and which resources they can access. Identifies attack paths and excessive permissions. Essential for IAM security audits and least-privilege implementation. Command-line tool with detailed reports.

### Azure Security

- **[Azure Security Center](https://azure.microsoft.com/en-us/services/security-center/)** - Unified security management platform for Azure resources. Provides security posture management, threat protection, and compliance dashboards. Includes vulnerability assessment for VMs, containers, and SQL databases. Microsoft Defender integration for advanced threat protection. Free tier available with basic security hygiene checks.

- **[Azure Sentinel](https://azure.microsoft.com/en-us/services/azure-sentinel/)** - Cloud-native SIEM and SOAR platform built on Azure. Collects data from Microsoft and third-party sources, uses AI to detect threats, and automates response. Integrates with Azure Security Center, Microsoft 365 Defender, and 100+ connectors. Scales to petabytes of data. Great for organizations using Microsoft ecosystem.

- **[AzureHound](https://github.com/BloodHoundAD/AzureHound)** - Azure data collector for BloodHound that maps Azure AD relationships and permissions. Identifies attack paths to privileged accounts, service principals, and resources. Essential for Azure AD security assessments and red team operations. Visualizes complex permission relationships in graph format.

### GCP Security

- **[Security Command Center](https://cloud.google.com/security-command-center)** - Google Cloud's centralized security and risk management platform. Provides asset discovery, vulnerability detection, threat detection, and compliance monitoring. Integrates with Web Security Scanner, Event Threat Detection, and Container Threat Detection. Premium tier includes advanced threat detection and security analytics.

- **[Forseti Security](https://forsetisecurity.org/)** - Open-source security toolkit for GCP (now part of Google's Security Command Center). Performs inventory management, policy enforcement, and security scanning. Checks IAM policies, firewall rules, storage permissions, and more. Automated remediation capabilities. Essential for GCP security at scale.

### Container & Kubernetes Security

See dedicated section below.

---

## Container & Kubernetes Security

### Container Image Scanning

- **[Trivy](https://github.com/aquasecurity/trivy)** - Comprehensive vulnerability scanner for containers, filesystems, and git repositories. Detects OS packages, language-specific dependencies (npm, pip, gem, etc.), and IaC misconfigurations. Scans container images, running containers, and Kubernetes clusters. Fast (5 seconds per image), accurate, and easy to use. Supports CI/CD integration with exit codes based on severity. 15,000+ GitHub stars. Essential for DevSecOps pipelines.

- **[Clair](https://github.com/quay/clair)** - Open-source project from Red Hat for static analysis of container image vulnerabilities. Indexes images layer-by-layer and correlates with CVE databases. REST API for integration with registries and CI/CD. Continuously updates vulnerability databases. Used by Quay, Harbor, and major container registries. Great for centralized scanning infrastructure.

- **[Anchore](https://anchore.com/opensource/)** - Deep image inspection and vulnerability scanning platform. Performs static analysis, policy enforcement, and compliance checks. Generates Software Bill of Materials (SBOM). Compares images across builds to track changes. Enterprise version includes runtime protection. Open-source Anchore Engine available for community use.

- **[Grype](https://github.com/anchore/grype)** - Fast vulnerability scanner for container images and filesystems from Anchore. Scans OS packages and language dependencies. Simple CLI interface with JSON output. Integrates easily into CI/CD pipelines. Uses multiple vulnerability databases (NVD, Alpine SecDB, etc.). Extremely fast compared to alternatives - great for large-scale scanning.

- **[Snyk Container](https://snyk.io/product/container-vulnerability-management/)** - Developer-first container security with vulnerability detection, base image recommendations, and Dockerfile analysis. Integrates with Docker Hub, ECR, ACR, GCR, and more. Provides prioritized fix advice and tracks vulnerability trends. Free tier available for open-source projects. Great developer experience with IDE integrations.

### Kubernetes Security Scanning

- **[kubescape](https://github.com/kubescape/kubescape)** - Open-source Kubernetes security platform that scans clusters, YAML files, and Helm charts. Tests against NSA-CISA Kubernetes Hardening Guide, MITRE ATT&CK, CIS Benchmarks, and custom frameworks. Identifies misconfigurations, vulnerabilities, and RBAC risks. Provides risk scores and remediation guidance. CLI and visual dashboard available. 8,000+ GitHub stars.

- **[kube-bench](https://github.com/aquasecurity/kube-bench)** - Checks Kubernetes clusters against CIS Kubernetes Benchmark. Runs as DaemonSet or standalone. Tests master nodes, worker nodes, etcd, and policies. Identifies deviations from security best practices. Generates detailed reports with remediation steps. Essential for compliance audits and cluster hardening. Works with managed Kubernetes (EKS, AKS, GKE).

- **[kube-hunter](https://github.com/aquasecurity/kube-hunter)** - Hunts for security weaknesses in Kubernetes clusters through penetration testing. Runs as pod inside cluster or remotely. Tests for exposed dashboards, unprotected APIs, privilege escalation paths, and misconfigurations. Great for red team assessments and security validation. Helps identify attack paths before adversaries do.

- **[Falco](https://falco.org/)** - Cloud-native runtime security tool that detects anomalous activity in containers and Kubernetes. Monitors system calls via eBPF to detect threats like privilege escalation, shell execution, sensitive file access, and network activity. Rules engine with 100+ default rules. Integrates with Prometheus, ELK, and SIEM platforms. CNCF graduated project with strong community.

- **[Polaris](https://github.com/FairwindsOps/polaris)** - Kubernetes admission controller and dashboard for security and best practices. Validates pod configurations, security contexts, resource limits, and network policies. Prevents deployment of insecure workloads. Dashboard shows cluster-wide security posture. Includes 30+ built-in checks with custom policy support. Great for preventing security issues at deployment time.

### Container Runtime Security

- **[Sysdig Falco](https://falco.org/)** (see above) - Runtime threat detection for containers and Kubernetes.

- **[Tracee](https://github.com/aquasecurity/tracee)** - Runtime security and forensics using eBPF. Detects suspicious behavioral patterns in running containers and hosts. Low overhead with kernel-level visibility. Integrates with Falco rules. Great for threat hunting and incident response. Provides detailed security events with context.

- **[Tetragon](https://github.com/cilium/tetragon)** - eBPF-based security observability and runtime enforcement from Cilium project. Provides transparent security observability, runtime enforcement, and threat detection. Kernel-level visibility with minimal overhead. Tracks process execution, network connections, and file access. Perfect for zero-trust security models.

### Kubernetes Network Security

- **[Cilium](https://cilium.io/)** - eBPF-based networking, observability, and security for Kubernetes. Provides network policies, load balancing, encryption, and service mesh capabilities. Transparent encryption with WireGuard or IPsec. API-aware network security that understands HTTP, gRPC, and Kafka protocols. CNCF graduated project used by major cloud providers.

- **[Calico](https://www.tigera.io/project-calico/)** - Popular Kubernetes network policy engine with extensive security features. Implements network policies, microsegmentation, and encrypted data-in-transit. Supports multi-cluster networking and service mesh integration. Used by 100M+ containers worldwide. Open-source with enterprise support available.

### Docker Security

- **[Docker Bench Security](https://github.com/docker/docker-bench-security)** - Script that checks Docker daemon and container configurations against CIS Docker Benchmark. Tests for dozens of security best practices. Runs as container itself. Generates detailed report with pass/fail/warning statuses. Essential for Docker security audits and hardening.

- **[Hadolint](https://github.com/hadolint/hadolint)** - Dockerfile linter that identifies security issues and best practice violations. Checks for 50+ issues including unnecessary privileges, exposed secrets, and inefficient layer caching. Integrates with CI/CD pipelines and IDEs. Prevents security issues before images are built. Simple to use with clear explanations.

---

## Static Application Security Testing (SAST)

### Multi-Language SAST

- **[Semgrep](https://semgrep.dev/)** - Fast, lightweight static analysis tool that finds bugs and enforces code standards. Supports 20+ languages with 2,000+ pre-built rules. YAML-based rules are easy to write and customize. Runs locally, in CI/CD, or as GitHub App. Open-source with commercial features. Used by Dropbox, Snowflake, and thousands of companies. Detects OWASP Top 10, CWE Top 25, and custom patterns. 10x faster than traditional SAST tools.

- **[SonarQube](https://www.sonarqube.org/)** - Leading continuous code quality and security platform. Analyzes 30+ languages for bugs, vulnerabilities, code smells, and security hotspots. Provides quality gates to block vulnerable code. Integrates with Azure DevOps, Jenkins, GitHub Actions, GitLab CI. Tracks technical debt and security debt over time. Community edition free with unlimited analysis. 400,000+ installations worldwide.

- **[CodeQL](https://codeql.github.com/)** - Semantic code analysis engine from GitHub that treats code as data. Query language allows complex security pattern detection. Powers GitHub Advanced Security. Supports C/C++, C#, Go, Java, JavaScript, Python, Ruby. Excellent for finding complex vulnerabilities like injection flaws and logic errors. Free for open-source projects. Includes 2,000+ security queries.

- **[Checkmarx](https://www.checkmarx.com/)** - Enterprise SAST platform with comprehensive language support (25+ languages). Provides accurate analysis with low false-positive rates. Integrates with all major IDEs and CI/CD platforms. Includes developer training and remediation guidance. Enterprise features include incremental scanning and audit trails. Used by Fortune 500 companies.

- **[TigerGate.dev](https://www.tigergate.dev/)** - Comprehensive application security platform combining SAST, SCA, and secrets detection in unified workflow. Automated security gates block critical vulnerabilities in CI/CD with intelligent prioritization and auto-fix capabilities. Supports 25+ languages with developer-friendly remediation guidance and low false-positive rates.

### Language-Specific SAST

**JavaScript/TypeScript**

- **[ESLint Security Plugin](https://github.com/nodesecurity/eslint-plugin-security)** - Identifies security vulnerabilities in JavaScript code during linting. Detects SQL injection, XSS, command injection, and unsafe regular expressions. Integrates seamlessly into existing ESLint configurations. Catches security issues during development. Low false-positive rate.

- **[NodeJsScan](https://github.com/ajinabraham/NodeJsScan)** - Static security code scanner for Node.js applications. Uses pattern matcher and syntax-aware semantic code analysis. Identifies injection vulnerabilities, authentication bypasses, and misconfigurations. Generates detailed reports with OWASP mappings. Can scan entire projects or individual files.

**Python**

- **[Bandit](https://github.com/PyCQA/bandit)** - Security linter for Python code from PyCQA. Finds common security issues like SQL injection, hardcoded passwords, insecure deserializations, and dangerous function calls. Plugin architecture allows custom checks. Integrates with CI/CD pipelines via exit codes. Fast and lightweight. Over 100 built-in tests.

- **[Pyre](https://pyre-check.org/)** - Performant type checker for Python from Meta (Facebook). Performs type checking and security analysis. Identifies attribute errors, missing annotations, and security vulnerabilities. Incrementally analyzes code for fast feedback. Used internally at Meta for billion-line codebases.

**Java**

- **[SpotBugs](https://spotbugs.github.io/)** - Successor to FindBugs that uses static analysis to find bugs in Java code. Includes FindSecBugs plugin for security-specific checks. Detects SQL injection, XSS, XXE, weak cryptography, and 130+ security bug patterns. Integrates with Maven, Gradle, and CI/CD. GUI and command-line interfaces available.

- **[Find Security Bugs](https://find-sec-bugs.github.io/)** - SpotBugs plugin focused on security audits of Java web applications. Detects OWASP Top 10 vulnerabilities, crypto issues, and framework-specific vulnerabilities (Spring, Struts, JSF). Covers 130+ bug patterns with detailed explanations. Essential for Java security testing.

**C/C++**

- **[Cppcheck](http://cppcheck.sourceforge.net/)** - Static analysis tool for C/C++ code. Detects undefined behavior, memory leaks, null pointer dereferences, buffer overflows, and more. Fast analysis with low false-positive rate. Supports MISRA C/C++ standards. Command-line and GUI interfaces. Integrates with major IDEs.

- **[Clang Static Analyzer](https://clang-analyzer.llvm.org/)** - Deep static analysis for C/C++ and Objective-C from LLVM project. Finds memory leaks, use-after-free, null pointer dereferences, and security vulnerabilities. Integrated into Xcode and scan-build tool. Advanced symbolic execution engine. Used by Apple, Google, and major tech companies.

**Go**

- **[Gosec](https://github.com/securego/gosec)** - Security scanner for Go source code that inspects for common security problems. Checks for SQL injection, file permissions, weak crypto, and 30+ security issues. Generates reports in JSON, CSV, HTML. Integrates with CI/CD pipelines. Fast and easy to use.

- **[GoKart](https://github.com/praetorian-inc/gokart)** - Static analysis tool for Go that tracks taint from sources to sinks. Finds injection vulnerabilities, XXE, SSRF, and path traversals. Designed for security researchers and pentesters. Outputs detailed vulnerability chains. Great for complex Go applications.

**Ruby**

- **[Brakeman](https://brakemanscanner.org/)** - Security scanner specifically for Ruby on Rails applications. Analyzes Rails app code for security vulnerabilities without running code. Detects SQL injection, XSS, mass assignment, and 25+ vulnerability types. Fast scanning with incremental analysis. Detailed confidence ratings. Essential for Rails security.

**PHP**

- **[RIPS](https://github.com/ripsscanner/rips)** - Static code analyzer for PHP vulnerabilities. Uses taint analysis to track user input through application. Detects injection flaws, XSS, file inclusions, and authentication issues. Open-source version available on GitHub. Commercial version offers more features.

---

## Dynamic Application Security Testing (DAST)

### Web Application DAST

- **[OWASP ZAP](https://www.zaproxy.org/)** (see Web Application Security section above) - Leading open-source DAST tool for web applications.

- **[Acunetix](https://www.acunetix.com/)** - Commercial web vulnerability scanner with industry-leading accuracy. Detects 7,000+ vulnerabilities including SQL injection, XSS, XXE, SSRF, and misconfigurations. Advanced crawling handles JavaScript-heavy SPAs and authenticated areas. Integrates with issue trackers and CI/CD. Includes vulnerability management and compliance reporting. Used by 9,000+ organizations.

- **[Netsparker (Invicti)](https://www.invicti.com/)** - Automated web application security scanner with proof-based scanning technology. Reduces false positives by proving vulnerabilities are real. Covers OWASP Top 10, CWE Top 25, and PCI-DSS requirements. Scans traditional and modern web apps. Integrates with JIRA, Azure DevOps, ServiceNow. Strong REST API for automation.

- **[Detectify](https://detectify.com/)** - Continuous web security scanner powered by ethical hackers. Crowdsources security tests from 350+ security researchers. Monitors for vulnerabilities, subdomain takeovers, and misconfigurations. Asset discovery finds all public-facing assets. Great for bug bounty programs and external attack surface management. SaaS-based with no installation needed.

### API DAST

- **[OWASP ZAP](https://www.zaproxy.org/)** - Excellent API testing capabilities including REST, SOAP, GraphQL support.

- **[Astra Security](https://www.getastra.com/)** - Continuous security testing platform for web apps and APIs. Tests OWASP Top 10, business logic flaws, and API vulnerabilities. Provides pentest-grade scanning with low false positives. Compliance reporting for PCI-DSS, GDPR, SOC 2. Managed service with expert security team.

---

## Software Composition Analysis (SCA)

### Dependency Scanning

- **[OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)** - Software Composition Analysis tool that identifies known vulnerabilities in project dependencies. Supports Java, .NET, JavaScript, Ruby, Python, and more. Scans dependency files and matches against NVD CVE database. Generates detailed reports with CVSS scores. Integrates with Maven, Gradle, Jenkins, Azure DevOps. Free and open-source. Essential for supply chain security.

- **[Snyk Open Source](https://snyk.io/product/open-source-security-management/)** - Developer-first SCA platform for finding and fixing vulnerable dependencies. Supports 10+ languages and package managers. Provides prioritized fix advice with automatic pull requests. Monitors projects continuously for new vulnerabilities. Integrates with GitHub, GitLab, Bitbucket, Azure Repos. Free tier available. Excellent developer experience with IDE plugins.

- **[WhiteSource (Mend)](https://www.mend.io/)** - Enterprise SCA platform with comprehensive dependency management. Covers 200+ programming languages and package managers. Provides license compliance, vulnerability detection, and policy enforcement. Automated remediation with suggested fixes. Real-time alerts for new vulnerabilities. Used by Microsoft, IBM, and Fortune 100 companies.

- **[Black Duck](https://www.synopsys.com/software-integrity/security-testing/software-composition-analysis.html)** - Comprehensive SCA solution from Synopsys. Identifies open-source components, vulnerabilities, and license risks. Binary scanning detects components without source code. Supports containers, build systems, and 25+ languages. Enterprise features include policy management and advanced reporting. Used for M&A due diligence.

- **[GitHub Dependabot](https://github.com/dependabot)** - Automated dependency updates and security alerts for GitHub repositories. Monitors dependencies for vulnerabilities and outdated versions. Creates pull requests with updates and release notes. Supports 10+ ecosystems including npm, pip, Maven, NuGet. Free for public and private repositories. Powered by GitHub Advisory Database.

- **[Renovate](https://github.com/renovatebot/renovate)** - Universal dependency update tool that supports 60+ platforms and package managers. Automates dependency updates with customizable schedules and grouping. More flexible than Dependabot with extensive configuration options. Self-hosted or SaaS options available. Great for monorepos and complex projects.

### License Compliance

- **[FOSSA](https://fossa.com/)** - Open-source license compliance and dependency management platform. Scans codebases for license obligations and vulnerabilities. Provides real-time compliance monitoring and policy enforcement. Generates compliance reports and SBOMs. Integrates with CI/CD and legal workflows. Used by Uber, Cisco, and thousands of companies.

- **[FOSSology](https://www.fossology.org/)** - Open-source license compliance software system. Analyzes source code for license information and copyright statements. Supports complex license scenarios and multi-license components. Web-based UI for review and reporting. Great for organizations needing detailed license analysis.

### Supply Chain Security

- **[Sigstore](https://www.sigstore.dev/)** - Open-source project for signing, verifying, and protecting software supply chains. Provides Cosign (container signing), Fulcio (certificate authority), and Rekor (transparency log). Non-profit backed by Linux Foundation. Used by Kubernetes, npm, and major projects. Essential for zero-trust software supply chains.

- **[in-toto](https://in-toto.io/)** - Framework to protect software supply chain integrity. Provides cryptographic verification of all steps in build pipeline. Prevents tampering and ensures reproducible builds. Integrated into major cloud platforms and CNCF projects. Excellent for high-security environments.

---

## Secrets Management & Detection

### Secrets Detection

- **[Gitleaks](https://github.com/gitleaks/gitleaks)** - Fast, lightweight secrets scanner for git repositories. Detects 300+ secret types including API keys, tokens, private keys, and credentials. Scans commits, branches, and entire git history. Pre-commit hooks prevent secret commits. CI/CD integration with exit codes. SARIF output for GitHub Security. 13,000+ GitHub stars. Essential for preventing credential leaks.

- **[TruffleHog](https://github.com/trufflesecurity/trufflehog)** - Searches git repositories for secrets by digging deep into commit history. Uses entropy detection and regex patterns to find credentials. Scans GitHub, GitLab, S3 buckets, and filesystems. Verifies findings by actually testing credentials (optional). Fast parallel scanning. Great for security audits and incident response.

- **[detect-secrets](https://github.com/Yelp/detect-secrets)** - Enterprise-friendly secrets detection tool from Yelp. Uses intelligent heuristics to minimize false positives. Baseline file tracks known secrets for auditing. Pre-commit hooks prevent accidental commits. Supports custom plugins for proprietary secrets. Excellent for large organizations with complex codebases.

- **[GitGuardian](https://www.gitguardian.com/)** - Real-time secrets detection for code repositories and CI/CD. Monitors GitHub, GitLab, Bitbucket, Azure DevOps. Detects 350+ secret types with low false-positive rate. Automated incident response and developer alerts. Dashboard shows historical trends and team metrics. Free for open-source projects and small teams.

- **[SpectralOps](https://spectralops.io/)** - Developer-native secrets detection and security monitoring. Scans code, CI/CD pipelines, logs, and infrastructure. Machine learning reduces false positives. Provides security guardrails throughout SDLC. Integrates with 50+ tools. Good developer experience with CLI and IDE plugins.

### Secrets Management

- **[HashiCorp Vault](https://www.vaultproject.io/)** - Industry-leading secrets management platform for any application. Securely stores and controls access to tokens, passwords, certificates, and API keys. Dynamic secrets for databases, cloud providers, and more. Encryption as a service with key management. Identity-based access with detailed audit logs. Used by 10,000+ organizations. Open-source with enterprise features available.

- **[AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)** - Managed service for rotating, managing, and retrieving database credentials, API keys, and secrets. Automatic rotation for RDS, Redshift, and DocumentDB. Fine-grained IAM policies for access control. Integrates with Lambda, ECS, EKS. Encrypted at rest and in transit. Pay-per-secret pricing. Native AWS integration.

- **[Azure Key Vault](https://azure.microsoft.com/en-us/services/key-vault/)** - Cloud service for safeguarding cryptographic keys and secrets. HSM-backed key storage meets FIPS 140-2 standards. Centralized secrets management for Azure services. Supports certificates, keys, and secrets. Azure AD integration for authentication. Detailed access logs for compliance. Good choice for Azure-centric organizations.

- **[Google Secret Manager](https://cloud.google.com/secret-manager)** - GCP service for storing API keys, passwords, certificates, and sensitive data. Automatic replication and versioning. IAM integration for fine-grained access control. Audit logging via Cloud Audit Logs. Integrates with GKE, Cloud Functions, App Engine. Simple API for secret access. Pay-per-secret pricing.

- **[Doppler](https://www.doppler.com/)** - Modern secrets management platform for teams and applications. Centralized secrets across all environments (dev, staging, prod). Syncs to cloud providers, CI/CD, and applications. Access controls and audit logs. CLI and SDKs for 10+ languages. Great developer experience. Free tier available.

- **[Infisical](https://infisical.com/)** - Open-source secrets management platform for developers. End-to-end encrypted secrets storage. Multi-environment support (dev, staging, prod). CLI, SDKs, and native integrations. Self-hosted or cloud options. Simpler alternative to Vault. Great for startups and small teams.

---

## Penetration Testing

### Penetration Testing Frameworks

- **[Metasploit Framework](https://www.metasploit.com/)** - World's most popular penetration testing framework with 2,200+ exploits, 1,100+ payloads, and 800+ auxiliary modules. Automates exploitation, post-exploitation, and pivoting. Extensive database of known vulnerabilities. Community edition is open-source. Commercial Metasploit Pro adds automation and reporting. Essential for penetration testers and red teams. Regularly updated with latest exploits.

- **[Cobalt Strike](https://www.cobaltstrike.com/)** - Commercial adversary simulation and red team operations platform. Features beacon payload for C2 communications, malleable profiles for traffic customization, and team collaboration. Used by red teams and advanced adversaries. Advanced post-exploitation capabilities. Expensive but industry-standard for enterprise red teaming.

- **[Empire](https://github.com/EmpireProject/Empire)** - Post-exploitation framework for Windows and Active Directory environments. PowerShell and Python agents for Windows and Linux. Stealthy communication protocols and encrypted channels. Extensive module library for credential harvesting, lateral movement, and persistence. Open-source and actively maintained by BC Security.

- **[Covenant](https://github.com/cobbr/Covenant)** - .NET command and control framework focused on tradecraft and operational security. Web-based interface for team collaboration. Multi-platform implants (Windows, Linux, macOS). Task-oriented architecture for flexible operations. Great alternative to Cobalt Strike with similar capabilities but open-source.

### Network Penetration Testing

- **[Nmap](https://nmap.org/)** (see Network Security section)

- **[Responder](https://github.com/lgandx/Responder)** - LLMNR, NBT-NS, and MDNS poisoner for credential theft on Windows networks. Captures NTLMv1/v2 hashes from network authentication attempts. Essential for internal penetration tests. Often first step in Active Directory attacks. Pairs well with hash cracking tools.

- **[CrackMapExec](https://github.com/byt3bl33d3r/CrackMapExec)** - Swiss Army knife for penetration testing Active Directory networks. Automates password spraying, hash dumping, lateral movement, and exploit deployment. Supports SMB, SSH, WinRM, MSSQL, LDAP. Extremely powerful for red team operations. 6,000+ GitHub stars.

- **[Impacket](https://github.com/SecureAuthCorp/impacket)** - Collection of Python classes for working with network protocols. Includes tools for SMB, MSSQL, TDS, LDAP, Kerberos manipulation. Essential for Windows penetration testing and Active Directory attacks. Powers many popular security tools. Well-maintained by SecureAuth.

### Web Application Penetration Testing

- **[Burp Suite Professional](https://portswigger.net/burp/pro)** (see Web Application Security section)

- **[sqlmap](https://sqlmap.org/)** - Automatic SQL injection and database takeover tool. Supports 20+ database engines with fingerprinting, data extraction, file system access, and OS command execution. Extensive tamper scripts for WAF bypass. Essential for testing SQL injection vulnerabilities. Most popular SQL exploitation tool with 25,000+ GitHub stars.

- **[XSStrike](https://github.com/s0md3v/XSStrike)** - Advanced XSS detection suite with fuzzing engine, intelligent payload generator, and WAF bypass capabilities. Analyzes HTML context and generates context-aware payloads. Detects blind XSS and out-of-band vulnerabilities. Excellent for bug bounty hunters.

- **[NoSQLMap](https://github.com/codingo/NoSQLMap)** - Automated penetration testing tool for MongoDB, CouchDB, Redis, and other NoSQL databases. Exploits injection vulnerabilities, authentication bypasses, and misconfigurations. Less common than SQL injection but increasingly important as NoSQL adoption grows.

### Wireless Penetration Testing

- **[Aircrack-ng](https://www.aircrack-ng.org/)** - Complete suite for wireless network security assessment. Captures packets, cracks WEP/WPA/WPA2-PSK keys, attacks WPS, and tests wireless card capabilities. Industry-standard for over 15 years. Includes airodump-ng (capture), aircrack-ng (cracking), aireplay-ng (injection), and more. Essential for wireless security testing.

- **[Wifite](https://github.com/derv82/wifite2)** - Automated wireless attack tool that simplifies aircrack-ng. Attacks multiple networks automatically, handles all authentication types, and sorts by signal strength. Great for pentesters needing quick WiFi assessments. Python-based with minimal configuration required.

- **[Kismet](https://www.kismetwireless.net/)** - Wireless network detector, sniffer, and IDS. Passive monitoring doesn't transmit packets. Detects hidden networks, tracks devices, and logs channel usage. Supports WiFi, Bluetooth, Zigbee, and SDR. Web-based interface with real-time updates. Essential for wireless reconnaissance.

### Exploitation Databases

- **[Exploit Database](https://www.exploit-db.com/)** - Archive of public exploits and vulnerable software from Offensive Security. 47,000+ exploits searchable by platform, type, and CVE. Includes Google Hacking Database and Papers. Essential resource for penetration testers. Command-line tool 'searchsploit' for offline searching.

- **[VulnHub](https://www.vulnhub.com/)** - Collection of vulnerable machines for practicing penetration testing. 600+ VMs covering various difficulty levels and attack vectors. Great for learning and CTF practice. Community-driven with write-ups available.

---

## Vulnerability Management

### Vulnerability Scanners

- **[OpenVAS](https://www.openvas.org/)** - Full-featured open-source vulnerability scanner with 70,000+ network vulnerability tests. Formerly part of Nessus before commercial fork. Tests for misconfigurations, outdated software, missing patches, and security issues. Web-based interface (Greenbone Security Assistant). Scheduled scanning and comprehensive reporting. Free alternative to commercial scanners.

- **[Nessus](https://www.tenable.com/products/nessus)** - Industry-leading commercial vulnerability scanner from Tenable. 165,000+ plugins covering all major platforms and applications. Accurate scanning with low false-positive rate. Compliance scanning for PCI-DSS, HIPAA, CIS benchmarks. Easy-to-use interface with customizable reports. Professional and Expert editions available. Used by 30,000+ organizations worldwide.

- **[Rapid7 Nexpose/InsightVM](https://www.rapid7.com/products/insightvm/)** - Vulnerability management solution with real-time risk analytics. Live dashboards show current risk posture. Integrates with Metasploit for exploit verification. Adaptive security for dynamic environments. Remediation workflows with ticketing system integration. Cloud-based or on-premises deployment.

- **[Qualys VMDR](https://www.qualys.com/apps/vulnerability-management-detection-response/)** - Cloud-based vulnerability management, detection, and response platform. Continuous monitoring with agent and agentless scanning. Asset discovery across cloud, on-prem, and endpoints. Prioritization based on threat intelligence and exploitability. Automated patch management integration. Scales to millions of assets.

### Patch Management

- **[GreenBone Security Manager (GSM)](https://www.greenbone.net/)** - Commercial version of OpenVAS with enhanced features. Centralized vulnerability management with compliance reporting. Automated workflows and patch management integration. Various appliance sizes available. Great for organizations wanting open-source scanning with enterprise support.

### Vulnerability Intelligence

- **[NIST NVD (National Vulnerability Database)](https://nvd.nist.gov/)** - U.S. government repository of standards-based vulnerability management data. 180,000+ CVE records with CVSS scores, descriptions, and references. Essential reference for security professionals. Provides CPE dictionary for software identification. Free public service.

- **[CVE Details](https://www.cvedetails.com/)** - Easy-to-use database for CVE security vulnerabilities. Provides statistics, vendor information, and vulnerability trends. Better search and filtering than raw NVD data. Free web interface with no registration required. Great for quick vulnerability research.

- **[VulnDB](https://vuldb.com/)** - Comprehensive vulnerability database with 400,000+ entries. Earlier disclosure than NVD in many cases. Includes exploits, threat intelligence, and remediation information. Commercial API available for integration. Good for proactive vulnerability management.

---

## Security Automation & Orchestration

### AI Agent Runtime Protection

- **[HOL Guard](https://hol.org/guard)** - Open-source security layer for AI coding agents and tools. It reviews supported shell commands, file access, package installs, and MCP actions before execution, then allows, blocks, or requests approval under local policy. It also scans plugins and agent configuration, records local decision receipts, and runs without a cloud account. Optional cloud features add shared history and team policy. Apache-2.0 licensed.

### SOAR Platforms

- **[TheHive](https://thehive-project.org/)** - Open-source Security Incident Response Platform. Case management with customizable templates, task automation, and observable enrichment. Integrates with MISP, Cortex analyzers, and 50+ tools. REST API for automation. Web-based collaboration interface. Used by SOC teams worldwide. Commercial support available.

- **[Cortex](https://github.com/TheHive-Project/Cortex)** - Powerful observable analysis engine for TheHive. 150+ analyzers for enrichment (VirusTotal, Shodan, etc.) and response actions (block IP, delete email, etc.). Create custom analyzers with simple API. Parallel execution for speed. Essential companion to TheHive.

- **[Shuffle](https://shuffler.io/)** - Open-source SOAR platform for security teams. Visual workflow builder with 500+ app integrations. Automated playbooks for common security scenarios. Cloud or on-premises deployment. Growing community with shared workflows. Modern alternative to commercial SOAR platforms.

- **[StackStorm](https://stackstorm.com/)** - Event-driven automation platform for auto-remediation, security responses, troubleshooting, and deployments. 6,000+ automation actions across 160+ packs. If-this-then-that rules for complex workflows. Python-based with strong community. Used for DevOps and security automation.

### Security Orchestration

- **[Splunk SOAR (formerly Phantom)](https://www.splunk.com/en_us/software/splunk-security-orchestration-and-automation-response.html)** - Enterprise SOAR platform for automating security operations. 350+ app integrations with security tools. Visual playbook editor with 2,000+ prebuilt actions. Case management and collaboration. Machine learning for prioritization. Used by Fortune 500 companies.

- **[IBM QRadar SOAR](https://www.ibm.com/security/security-orchestration-automation-response)** - Security orchestration platform integrated with QRadar SIEM. Automated incident response playbooks reduce MTTR. Pre-built integrations with 275+ security products. Playbook designer with Python scripting. Enterprise-grade with 24/7 support.

### Infrastructure as Code Security

- **[Terraform Sentinel](https://www.terraform.io/docs/cloud/sentinel/index.html)** - Policy-as-code framework for Terraform from HashiCorp. Enforces security standards before infrastructure deployment. Prevents misconfigurations and compliance violations. Write policies in Sentinel language. Integrates with Terraform Cloud. Essential for cloud infrastructure security.

- **[Chef InSpec](https://www.chef.io/products/chef-inspec)** - Open-source testing framework for infrastructure compliance. Tests actual system state against desired state. Supports Windows, Linux, Docker, Kubernetes, cloud APIs. Human-readable DSL for writing tests. CI/CD integration for automated compliance. 100+ pre-built compliance profiles.

---

## Compliance & Auditing

### Compliance Frameworks

- **[OpenSCAP](https://www.open-scap.org/)** - Open-source implementation of SCAP (Security Content Automation Protocol). Automated compliance evaluation and system hardening. Supports CIS, STIG, PCI-DSS, HIPAA benchmarks. Command-line and GUI tools available. Works with Red Hat, CentOS, Ubuntu. Essential for government and regulated industries.

- **[Lynis](https://cisofy.com/lynis/)** - Security auditing tool for Unix/Linux systems. Performs 300+ security checks including hardening, malware scanning, and compliance. Generates detailed reports with recommendations. Lightweight shell script runs without agent. Commercial support and dashboard available. Great for DevOps security.

- **[Vanta](https://www.vanta.com/)** - Automated compliance platform for SOC 2, ISO 27001, HIPAA, GDPR, and more. Continuous monitoring of security controls with real-time evidence collection. Integrates with 50+ cloud services and tools. Reduces audit preparation from months to weeks. Dashboard shows compliance posture. Used by 4,000+ companies.

- **[Drata](https://drata.com/)** - Compliance automation platform for growing companies. Supports SOC 2, ISO 27001, PCI-DSS, HIPAA, GDPR. Continuous monitoring and automated evidence collection. Security training and policy management included. Streamlines security questionnaires. Great for startups pursuing first compliance certification.

- **[LowerPlane](https://lowerplane.com/)** - Automated compliance platform for SOC 2, ISO 27001, HIPAA, PCI-DSS, GDPR through continuous monitoring and evidence collection. Features 200+ integrations with cloud providers and security tools. Policy-as-code engine with pre-built control libraries. Reduces audit preparation time by 80% with automated evidence gathering and remediation workflows. Significantly more affordable than traditional GRC platforms.

### Configuration Management

- **[Ansible](https://www.ansible.com/)** - Agentless automation platform for configuration management, application deployment, and security hardening. Playbooks written in YAML are easy to read and write. 5,000+ modules for managing systems and services. Security automation playbooks available from community. Open-source with Red Hat support.

- **[Puppet](https://puppet.com/)** - Infrastructure automation and configuration management. Declarative language defines desired state. Agent-based architecture ensures continuous compliance. Security modules for hardening and vulnerability remediation. Enterprise features include rbac and reporting. Used by 40,000+ organizations.

- **[Chef](https://www.chef.io/)** - Infrastructure automation with code. Configuration management, compliance, and security automation. Test-driven infrastructure with InSpec integration. Large community with 10,000+ cookbooks. Ruby-based DSL for configuration recipes. Enterprise and open-source versions.

### Security Benchmarks

- **[CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks/)** - 140+ configuration guidelines for securing IT systems and data. Covers operating systems, cloud platforms, network devices, and applications. Consensus-developed by security experts globally. Free PDF downloads. OpenSCAP and Lynis implement these benchmarks. Industry-standard hardening guides.

- **[DISA STIGs](https://public.cyber.mil/stigs/)** - Security Technical Implementation Guides from U.S. Defense Information Systems Agency. Mandatory for DoD systems, widely adopted in government. Comprehensive security settings for 500+ technologies. Automated checking with SCAP content. More stringent than CIS benchmarks.

### Audit Logging

- **[Auditd](https://linux.die.net/man/8/auditd)** - Linux kernel auditing system that logs security events. Tracks file access, system calls, user actions, and configuration changes. Essential for compliance, forensics, and intrusion detection. Low overhead with high reliability. Ships with all modern Linux distributions.

- **[Osquery](https://osquery.io/)** - SQL-powered operating system instrumentation and analytics. Query OS like a relational database for inventory, monitoring, and forensics. Cross-platform (Windows, Linux, macOS). Used for endpoint visibility, compliance, and threat hunting. Open-source from Meta (Facebook). 20,000+ GitHub stars.

---

## Incident Response & Forensics

### Incident Response Platforms

- **[TheHive](https://thehive-project.org/)** (see Security Automation section) - Open-source incident response platform.

- **[DFIR-IRIS](https://github.com/dfir-iris/iris-web)** - Collaborative incident response platform for sharing investigations. Case management with timelines, evidence tracking, and reporting. Role-based access control for team collaboration. Integrates with MISP, Cortex, and forensic tools. Modern web interface with REST API.

- **[Velociraptor](https://www.velocidex.com/)** - Advanced endpoint visibility and digital forensics tool. Deploys agents for live response, hunt for threats, and collect forensic artifacts. Uses VQL (Velociraptor Query Language) for flexible data collection. Scales to 10,000+ endpoints. Open-source with commercial support. Excellent for threat hunting.

- **[GRR Rapid Response](https://github.com/google/grr)** - Remote live forensics framework from Google. Scalable to 100,000+ endpoints with centralized management. Collects forensic artifacts without disrupting systems. Powerful hunting capabilities with flow-based automation. Used by large enterprises and government agencies.

### Forensic Tools

- **[Autopsy](https://www.autopsy.com/)** - Digital forensics platform with graphical interface. Analyzes hard drives, smartphones, and media cards. File carving, timeline analysis, keyword search, and deleted file recovery. Extensible via Python modules. Based on The Sleuth Kit. Free, open-source, and user-friendly. Essential for forensic investigations.

- **[The Sleuth Kit](https://www.sleuthkit.org/)** - Collection of command-line tools for digital forensics. Analyzes disk images and file systems (NTFS, FAT, ext, HFS+). Used by Autopsy as analysis engine. Industry-standard for 20+ years. Forensically sound with detailed documentation. Essential for forensic examiners.

- **[Volatility](https://www.volatilityfoundation.org/)** - Advanced memory forensics framework. Analyzes RAM dumps to extract processes, network connections, crypto keys, and malware artifacts. Supports Windows, Linux, macOS, Android. Plugin architecture for extensibility. Essential for malware analysis and incident response. Used by forensic professionals worldwide.

- **[Rekall](http://www.rekall-forensic.com/)** - Memory forensic framework from Google (formerly Google Rapid Response). Similar to Volatility with enhanced performance. Live memory analysis without creating dump. Excellent for large-scale investigations. Supports multiple platforms.

### Disk Imaging & Analysis

- **[FTK Imager](https://www.exterro.com/ftk-imager)** - Free forensic imaging tool from AccessData. Creates forensically sound disk images (E01, DD, AFF). Mounts images as read-only for analysis. Preview files without altering evidence. Industry-standard for forensic acquisition. Windows-based with simple interface.

- **[dd / dcfldd](https://linux.die.net/man/1/dd)** - Unix tools for creating forensic disk images. Command-line utilities available on all Linux systems. Create bit-for-bit copies with hash verification. dcfldd adds progress monitoring and forensic features. Free and reliable for forensic imaging.

### Log Analysis

- **[Splunk](https://www.splunk.com/)** - Leading platform for searching, monitoring, and analyzing machine data. Ingests logs from any source with real-time indexing. Powerful search language (SPL) for complex queries. Security analytics, dashboards, and alerting. Splunk Enterprise Security (ES) for SOC operations. Free tier available for 500MB/day.

- **[Elasticsearch/Logstash/Kibana (ELK Stack)](https://www.elastic.co/elastic-stack)** - Open-source log analysis platform. Logstash collects and parses logs, Elasticsearch indexes and searches, Kibana visualizes. Scales to petabytes of data. Security analytics with machine learning. Free and open-source with commercial support available.

- **[Graylog](https://www.graylog.org/)** - Open-source log management platform with enterprise features. Centralized logging, real-time search, and alerting. Stream processing for enrichment and normalization. Built on Elasticsearch with MongoDB for metadata. Easier to manage than ELK Stack. Free open-source version available.

### Malware Analysis

- **[Cuckoo Sandbox](https://cuckoosandbox.org/)** - Automated malware analysis system. Runs suspicious files in isolated environment and generates detailed reports. Monitors API calls, network traffic, and file system changes. Supports Windows, Linux, macOS, Android. Excellent for analyzing unknown binaries. Open-source and actively developed.

- **[Any.Run](https://any.run/)** - Interactive malware analysis service in the browser. Real-time sandbox with full control over VM. Observe malware behavior without local risks. Public submissions available for research. Great for quick analysis and IOC extraction. Freemium model with paid plans.

- **[Hybrid Analysis](https://www.hybrid-analysis.com/)** - Free malware analysis service powered by Falcon Sandbox. 100,000+ malware samples analyzed daily. Static and dynamic analysis with detailed reports. Threat intelligence and IOC extraction. API available for integration. Excellent free resource for security researchers.

- **[VirusTotal](https://www.virustotal.com/)** - Analyzes files and URLs using 70+ antivirus engines. Provides reputation scores, behavioral information, and community comments. Essential for quick threat assessment. API available for automated scanning. Free for limited usage, premium for higher limits. Owned by Google.

---

## Threat Intelligence

### Threat Intelligence Platforms

- **[MISP (Malware Information Sharing Platform)](https://www.misp-project.org/)** - Open-source threat intelligence platform for sharing, storing, and correlating IOCs. 150+ threat intel feeds integrated. Taxonomies for categorizing threats. Event correlation and visualization. API for automation. 6,000+ organizations use MISP. Essential for threat intelligence sharing communities.

- **[OpenCTI](https://www.opencti.io/)** - Open-source cyber threat intelligence platform. Structured data model following STIX 2.1 standard. Visualizes relationships between threat actors, campaigns, and IOCs. 60+ connectors for threat intel sources. Knowledge graph with advanced queries. Modern UI with collaboration features.

- **[AlienVault OTX](https://otx.alienvault.com/)** - Open Threat Exchange - community-driven threat intelligence. 19M+ IOCs from 150,000+ participants globally. Pulse system shares threat campaigns with IOCs and context. API for automated integration. Free to use and contribute. Great starting point for threat intel.

- **[ThreatConnect](https://threatconnect.com/)** - Enterprise threat intelligence platform. Aggregates data from 100+ sources. Threat analysis with diamond model and kill chain. Playbooks for automated response. Integrates with SIEMs, firewalls, and SOARs. Used by Fortune 500 and government agencies.

### Threat Feeds

- **[Abuse.ch](https://abuse.ch/)** - Collection of free threat intelligence feeds including MalwareBazaar, URLhaus, ThreatFox, and Feodo Tracker. Focus on malware samples, malicious URLs, and botnet C2s. Excellent reputation with low false positives. Free APIs available. Community-driven project.

- **[Spamhaus](https://www.spamhaus.org/)** - Leading intelligence on spam, phishing, malware, and botnets. Multiple blocklists (SBL, XBL, PBL, DBL) protect email and DNS. 3 billion+ DNS queries daily use Spamhaus data. Free for non-commercial use. Commercial data feeds available.

- **[Emerging Threats](https://rules.emergingthreats.net/)** - Open-source ruleset for Suricata, Snort, and other IDS/IPS. 20,000+ signatures updated daily. Covers malware, exploits, scans, and mobile malware. Free community rules with paid Pro version. Essential for network security monitoring.

### OSINT Tools

- **[Maltego](https://www.maltego.com/)** - Interactive data mining and link analysis tool. Visualizes relationships between people, companies, domains, IPs, and more. 50+ data sources integrated. Transform hub with custom transforms. Community edition free. Used by investigators, threat intel analysts, and pentesters.

- **[Shodan](https://www.shodan.io/)** (see Network Security section) - Search engine for Internet-connected devices providing excellent threat intelligence.

- **[Censys](https://censys.io/)** - Internet-wide scanning platform for asset discovery and threat intelligence. Scans Internet regularly for services, certificates, and configurations. Better certificate search than Shodan. Academic research tool from University of Michigan. Free tier available with API access.

- **[GreyNoise](https://www.greynoise.io/)** - Distinguishes malicious scanning from benign activity. Identifies mass scanning events, vulnerability exploitations, and noisy IPs. Reduces alert fatigue by filtering background noise. Community API free. Essential for SOC analysts and threat hunters.

---

## Security Monitoring & SIEM

### SIEM Platforms

- **[Splunk Enterprise Security](https://www.splunk.com/en_us/software/enterprise-security.html)** - Premium SIEM built on Splunk platform. Analytics-driven security with 1,500+ correlation searches. Notable events, incident review, and threat intelligence integration. Asset and identity tracking. Glass tables for SOC monitoring. Used by Fortune 500 companies. Expensive but powerful.

- **[Elastic Security (SIEM)](https://www.elastic.co/security/siem)** - SIEM built on Elasticsearch with threat hunting, detection, and response. Pre-built detection rules and machine learning jobs. Timeline investigation with drag-and-drop. Integrates with endpoint protection (Elastic Agent). Open-source with commercial features. More affordable than traditional SIEMs.

- **[IBM QRadar](https://www.ibm.com/products/qradar-siem)** - Enterprise SIEM for threat detection and compliance. Log management and network flow analysis. Real-time correlation with 500+ pre-built rules. Offense management for incident workflow. App Exchange with 200+ integrations. On-prem or cloud deployment.

- **[LogRhythm](https://logrhythm.com/)** - Unified SIEM, UEBA, and SOAR platform. SmartResponse automation for rapid response. Built-in UEBA detects insider threats and compromised accounts. Case management for investigations. All-in-one platform reduces tool sprawl. Mid-market focused.

- **[Wazuh](https://wazuh.com/)** (see Network Security section) - Open-source SIEM with XDR capabilities.

### Log Management

- **[Graylog](https://www.graylog.org/)** (see Incident Response section) - Open-source log management and analysis.

- **[Fluentd](https://www.fluentd.org/)** - Open-source data collector for unified logging. 650+ plugins for inputs and outputs. Buffers data for reliability. Low memory footprint. CNCF graduated project. Used by thousands of companies for log aggregation. Great for cloud-native applications.

- **[Filebeat](https://www.elastic.co/beats/filebeat)** - Lightweight log shipper from Elastic. Tails log files and forwards to Elasticsearch or Logstash. Modules for common applications (Apache, MySQL, Nginx). Guarantees at-least-once delivery. Low resource usage. Part of Beats family of shippers.

### Network Monitoring

- **[Zeek](https://zeek.org/)** (see Network Security section) - Network security monitor providing high-level network analysis.

- **[Moloch](https://molo.ch/)** - Large-scale packet capture and search system. Indexes PCAP data for fast searching. Web interface for viewing and analyzing captures. Scales to handle millions of packets per second. Great for forensics and threat hunting. Open-source with commercial support.

- **[Security Onion](https://securityonionsolutions.com/)** - Free Linux distribution for threat hunting, enterprise security monitoring, and log management. Combines Suricata, Zeek, Wazuh, Elastic Stack, and custom tools. Easy deployment with setup wizard. Includes pre-built dashboards and hunt queries. Excellent for building SOC on a budget.

### User Behavior Analytics (UEBA)

- **[Exabeam](https://www.exabeam.com/)** - UEBA and next-gen SIEM platform. Uses machine learning to detect anomalous behavior. Timeline-based investigations. Pre-built use cases for common attack patterns. Cloud-native architecture. Good for detecting insider threats and compromised accounts.

- **[Splunk UBA](https://www.splunk.com/en_us/software/user-behavior-analytics.html)** - Add-on for Splunk Enterprise providing UEBA capabilities. Machine learning detects threats from insiders and compromised accounts. Peer group analysis identifies anomalies. Reduces investigation time with context-rich alerts. Integrates with Splunk ES.

---

## API Security

### API Security Testing

- **[OWASP ZAP](https://www.zaproxy.org/)** (see Web Application Security) - Excellent API testing with OpenAPI/Swagger support.

- **[Postman](https://www.postman.com/)** (see Web Application Security) - API testing platform with security features.

- **[REST-Assured](https://rest-assured.io/)** - Java DSL for testing REST APIs. Validates JSON/XML responses with simple syntax. Supports authentication, cookies, and multipart uploads. Integrates with JUnit and TestNG. Great for automated API security testing in CI/CD.

### API Security Platforms

- **[Atatus](https://www.atatus.com)** - Real-time API security and observability platform for REST, GraphQL, and gRPC. Automated API discovery identifies shadow APIs while runtime protection blocks OWASP API Top 10 threats. Machine learning detects anomalous behavior and data exfiltration. Includes sensitive data discovery, performance monitoring, and distributed tracing.

- **[42Crunch](https://42crunch.com/)** - API security platform protecting entire API lifecycle. Static analysis of OpenAPI definitions (Security Audit). Runtime protection with API firewall. Dynamic testing with conformance scanning. Provides security scores for APIs. Good developer experience with IDE plugins.

- **[Salt Security](https://salt.security/)** - API security platform using machine learning. Discovers all APIs (shadow APIs). Prevents API attacks with runtime protection. Blocks OWASP API Top 10 threats. Used by financial services and healthcare. Enterprise-focused solution.

- **[Traceable AI](https://www.traceable.ai/)** - API security and observability platform. Discovers APIs and sensitive data flows. Detects threats with behavioral analysis. Integrates with API gateways. Good for microservices architectures. Cloud-native design.

### API Gateways with Security

- **[Kong Gateway](https://konghq.com/kong/)** - Cloud-native API gateway with extensive security plugins. Authentication (OAuth2, JWT, API keys), rate limiting, IP restriction, bot detection. Extensible via Lua plugins. Open-source with enterprise version. 35,000+ GitHub stars.

- **[Tyk](https://tyk.io/)** - Open-source API gateway and management platform. Built-in security features: authentication, quotas, rate limiting. GraphQL and REST support. Developer portal for API consumers. Dashboard for management. Good balance of features and simplicity.

---

## Mobile Security

### Mobile Application Security Testing

- **[MobSF (Mobile Security Framework)](https://github.com/MobSF/Mobile-Security-Framework-MobSF)** - All-in-one automated mobile app security assessment framework. Supports Android (APK, AAB) and iOS (IPA). Static and dynamic analysis. Identifies OWASP Mobile Top 10 vulnerabilities. Web interface with detailed reports. REST API for CI/CD integration. 15,000+ GitHub stars. Essential for mobile security testing.

- **[Objection](https://github.com/sensepost/objection)** - Runtime mobile exploration toolkit powered by Frida. Inspects and manipulates mobile apps without jailbreak/root. Dumps memory, hooks methods, bypasses SSL pinning, and more. Supports iOS and Android. Great for security research and penetration testing.

- **[Frida](https://frida.re/)** - Dynamic instrumentation toolkit for reverse engineering. Injects JavaScript into native apps on Windows, macOS, Linux, iOS, Android. Hooks functions, traces calls, and modifies behavior at runtime. Extensive API with Python bindings. Essential for mobile security research. Used by MobSF and Objection.

### Android Security

- **[APKTool](https://ibotpeaches.github.io/Apktool/)** - Reverse engineering tool for Android APK files. Decodes resources to original form. Rebuilds modified apps. Essential for Android security research. Simple command-line interface. Active development for 10+ years.

- **[Drozer](https://github.com/WithSecureLabs/drozer)** - Security testing framework for Android. Assumes role of Android app to interact with other apps. Tests for common vulnerabilities: exported components, content providers, SQL injection. Essential for Android pentesting. Originally from MWR, now maintained by WithSecure.

- **[Jadx](https://github.com/skylot/jadx)** - Dex to Java decompiler for Android APK analysis. GUI and command-line interfaces. Fast and accurate decompilation. Exports projects to Gradle for recompilation. Essential for analyzing Android malware and app security. 36,000+ GitHub stars.

### iOS Security

- **[iMazing](https://imazing.com/)** - iOS device manager for backup and file access. Extract app data for analysis. Doesn't require jailbreak. Great for iOS forensics and security research. Commercial tool with free trial.

- **[Checkra1n](https://checkra.in/)** - Semi-tethered jailbreak for iOS devices. Based on checkm8 bootrom exploit (permanent vulnerability). Required for deep iOS security research. Supports iOS 12-14. Community-developed tool.

---

## Database Security

### Database Security Scanning

- **[DbDefense](https://www.dbdefense.com/)** - Database security solution for Oracle, SQL Server, MySQL, PostgreSQL. Vulnerability assessment, privilege analysis, and compliance reporting. Identifies misconfigurations and weak passwords. Continuous monitoring for changes. Good for enterprise database security.

- **[Imperva Database Security](https://www.imperva.com/products/database-security/)** - Comprehensive database security platform. Database activity monitoring (DAM), database firewall, vulnerability assessment. Protects against SQL injection, privilege abuse, and data exfiltration. Compliance reporting for major regulations. Enterprise solution for critical databases.

### Database Firewalls

- **[GreenSQL](http://www.greensql.com/)** - Open-source database firewall for MySQL and PostgreSQL. SQL injection protection with pattern matching. Risk scoring engine identifies suspicious queries. Monitoring and alerting for database attacks. Lightweight with minimal performance impact.

### MongoDB Security

- **[MongoDB Enterprise Advanced](https://www.mongodb.com/products/mongodb-enterprise-advanced)** - Enterprise features including encryption, auditing, and LDAP integration. Field-level encryption protects sensitive data. Queryable encryption (preview). FIPS 140-2 compliant. Good for regulated industries.

### SQL Injection Testing

- **[sqlmap](https://sqlmap.org/)** (see Penetration Testing section) - Automatic SQL injection exploitation tool.

---

## Identity & Access Management

### Identity Providers

- **[Keycloak](https://www.keycloak.org/)** - Open-source identity and access management solution. SSO with OIDC, OAuth 2.0, and SAML support. Social login, user federation (LDAP/AD), and identity brokering. Highly customizable with themes and extensions. 18,000+ GitHub stars. Great alternative to Auth0 and Okta.

- **[Authelia](https://www.authelia.com/)** - Open-source authentication and authorization server. Two-factor authentication with various methods. SSO and single logout. Reverse proxy integration (Nginx, Traefik). Lightweight and easy to deploy. Good for homelab and small businesses.

- **[Authentik](https://goauthentik.io/)** - Open-source identity provider focused on flexibility and versatility. LDAP provider, OAuth2/OIDC provider, SAML IdP. Built-in MFA with TOTP, WebAuthn, and more. Policy engine for complex authorization. Modern UI and easy configuration.

### Multi-Factor Authentication

- **[privacyIDEA](https://www.privacyidea.org/)** - Open-source multi-factor authentication system. Supports TOTP, HOTP, SMS, email, push, U2F, WebAuthn. Integrates with LDAP, AD, and RADIUS. Web interface for user enrollment. On-premises deployment for maximum security.

- **[LinOTP](https://www.linotp.org/)** - Open-source two-factor authentication solution. Multiple token types: HOTP, TOTP, SMS, email, YubiKey. LDAP/AD integration. Scales to millions of users. Web interface for administration. Alternative to privacyIDEA.

### Access Control

- **[Open Policy Agent (OPA)](https://www.openpolicyagent.org/)** - Policy-based control for cloud-native environments. Decouples policy decisions from application code. Policies written in Rego declarative language. Kubernetes admission control, microservices authorization, and API gateways. CNCF graduated project. 8,000+ GitHub stars.

- **[Casbin](https://casbin.org/)** - Authorization library supporting ACL, RBAC, ABAC models. 50+ language implementations. Supports various storage adapters. Used by VMware, RedHat, IBM. Great for embedding authorization in applications.

### Privileged Access Management

- **[Teleport](https://goteleport.com/)** - Access platform for SSH, Kubernetes, databases, and web applications. Certificate-based access eliminates static credentials. Session recording for compliance. Single sign-on with GitHub, Google, Okta. Open-source with enterprise features. Great for DevOps teams.

- **[Boundary](https://www.boundaryproject.io/)** - HashiCorp's identity-based access management for dynamic infrastructure. Just-in-time credentials for databases, SSH, Kubernetes. No credential management or VPN required. Integrates with Vault for secrets. Modern approach to privileged access.

---

## Cryptography & PKI

### Certificate Management

- **[Let's Encrypt](https://letsencrypt.org/)** - Free, automated certificate authority providing SSL/TLS certificates. 300M+ websites use Let's Encrypt. 90-day certificates encourage automation. ACME protocol for automated issuance. Sponsored by major tech companies. Essential for web security.

- **[Certbot](https://certbot.eff.org/)** - Official Let's Encrypt client by EFF. Automatically obtains and installs certificates. Works with Apache, Nginx, and more. Automated renewal with cron jobs. Simple command-line interface. Essential companion to Let's Encrypt.

- **[cert-manager](https://cert-manager.io/)** - Kubernetes add-on for automated certificate management. Obtains certificates from Let's Encrypt, HashiCorp Vault, and others. Renews certificates before expiration. CRD-based configuration. Essential for Kubernetes TLS. CNCF project.

### PKI & Certificate Tools

- **[OpenSSL](https://www.openssl.org/)** - Robust, commercial-grade cryptography library. SSL/TLS implementation and command-line tools. Generate keys, CSRs, and certificates. Essential for any security professional. Industry-standard for 25+ years.

- **[CFSSL](https://github.com/cloudflare/cfssl)** - CloudFlare's PKI/TLS toolkit. Certificate authority for internal certificates. JSON API for automation. Intermediate CA support. Used by Kubernetes. Good for building internal PKI.

- **[Easy-RSA](https://github.com/OpenVPN/easy-rsa)** - CLI utility to build and manage PKI certificate authority. Originally part of OpenVPN project. Simple shell script interface. Good for small-scale PKI deployments. No database required.

### Encryption Tools

- **[VeraCrypt](https://www.veracrypt.fr/)** - Free open-source disk encryption software. Successor to TrueCrypt with enhanced security. Creates encrypted volumes or encrypts entire drives. Windows, macOS, Linux support. Excellent for protecting sensitive data at rest.

- **[GnuPG (GPG)](https://gnupg.org/)** - Complete implementation of OpenPGP standard. Encrypts and signs data. Key management and verification. Command-line with GUI frontends available. Essential for email encryption and file signing. Used by developers for package signing.

- **[Age](https://github.com/FiloSottile/age)** - Modern, simple file encryption tool. Alternative to GPG with better usability. Small explicit keys instead of keyring. Uses modern cryptography (ChaCha20-Poly1305, X25519). Great for encrypting files and backups.

### Hardware Security

- **[YubiKey](https://www.yubico.com/)** - Hardware authentication device supporting FIDO2, U2F, OTP, PIV, and OpenPGP. Passwordless authentication for websites and services. Extremely secure with tamper-resistant design. Used by Google employees. Various models available.

- **[SoloKeys](https://solokeys.com/)** - Open-source FIDO2 security key. Hardware and firmware are open-source. Supports passwordless and two-factor authentication. More affordable than YubiKey. Great for open-source enthusiasts.

---

## Security Training & CTF

### Capture The Flag (CTF) Platforms

- **[HackTheBox](https://www.hackthebox.com/)** - Leading platform for pentesting training. 400+ machines to hack (beginner to expert). Active community with 2M+ users. Realistic scenarios covering all pentesting domains. ProLabs for advanced team training. Academy for structured learning paths. Certifications available.

- **[TryHackMe](https://tryhackme.com/)** - Gamified cybersecurity training platform. Guided learning paths from beginner to advanced. 900+ hands-on labs and challenges. More beginner-friendly than HackTheBox. Active Discord community. Affordable subscription model. Great for learning security fundamentals.

- **[PentesterLab](https://pentesterlab.com/)** - Hands-on pentesting training platform. 100+ exercises covering web, network, and system security. Structured learning with badges for completion. Monthly subscription with new content regularly. Great for web application security focus.

- **[PicoCTF](https://picoctf.org/)** - Free CTF platform from Carnegie Mellon. Designed for high school and college students. Challenges across cryptography, forensics, web exploitation, binary exploitation. Annual competition with 100,000+ participants. Great for beginners.

- **[OverTheWire](https://overthewire.org/)** - Wargames teaching security concepts through challenges. Bandit teaches Linux basics. Natas focuses on web security. Multiple difficulty levels. Completely free. Great for learning fundamentals.

### Vulnerable Applications

- **[OWASP WebGoat](https://owasp.org/www-project-webgoat/)** - Deliberately insecure web application for learning. Lessons on OWASP Top 10 with hands-on exercises. Built-in hints and solutions. Java-based application runs locally. Essential for learning web security. Updated regularly.

- **[DVWA (Damn Vulnerable Web Application)](https://github.com/digininja/DVWA)** - PHP/MySQL vulnerable web app for testing skills and tools. Three difficulty levels. Covers SQL injection, XSS, CSRF, and more. Simple setup with Docker. Great for practicing manual testing.

- **[bWAPP (Buggy Web Application)](http://www.itsecgames.com/)** - Free and open-source deliberately insecure web app. 100+ web vulnerabilities across all risk levels. Educational tool for security professionals and students. Covers OWASP Top 10 and beyond.

- **[Mutillidae](https://github.com/webpwnized/mutillidae)** - Free, open-source vulnerable web application. OWASP Top 10 and beyond. Multiple security levels. Extensive hints and videos. Active development and documentation.

### Security Certifications

- **[OffSec (Offensive Security)](https://www.offensive-security.com/)** - Provider of OSCP (penetration testing), OSWE (web expert), OSEP (experienced pentester). "Try Harder" mentality with challenging practical exams. Industry-recognized certifications. Labs include hundreds of machines. Expensive but valuable.

- **[SANS/GIAC](https://www.giac.org/)** - Technical information security certifications. GSEC (security essentials), GCIH (incident handler), GPEN (penetration tester), and 30+ more. High-quality training with practitioner labs. Expensive but comprehensive. Recognized by DoD 8570.

- **[eLearnSecurity](https://www.ine.com/)** - Affordable alternative to OffSec with practical exams. eCPPT (penetration tester), eWPT (web pentester), eMAPT (mobile). More affordable than OSCP. Good for those on budget.

### Training Ranges

- **[Cyberbit Range](https://www.cyberbit.com/solutions/cyber-range/)** - Hyper-realistic cyber range for SOC training. Simulates real attacks on enterprise networks. Team-based scenarios with live attacks. Expensive but used by military and enterprises. Great for team training.

- **[RangeForce](https://www.rangeforce.com/)** - Cloud-based cyber skills training platform. Hands-on labs for security teams. Skill assessments and certifications. Used by enterprises for team development. Focuses on SOC and defensive skills.

---

## Security Frameworks & Standards

### Security Frameworks

- **[NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)** - Framework for managing cybersecurity risk. Five functions: Identify, Protect, Detect, Respond, Recover. Widely adopted by organizations of all sizes. Voluntary framework with flexible implementation. Free to use with extensive documentation.

- **[CIS Controls](https://www.cisecurity.org/controls/)** - Prioritized set of actions for cybersecurity defense. 18 controls organized by implementation group. Covers basic cyber hygiene to advanced. Metrics and tools for measuring progress. Free to download and use.

- **[ISO/IEC 27001](https://www.iso.org/isoiec-27001-information-security.html)** - International standard for information security management systems (ISMS). Certification demonstrates security commitment. Includes 114 controls across 14 categories. Recognized globally. Requires audit for certification.

- **[MITRE ATT&CK](https://attack.mitre.org/)** - Knowledge base of adversary tactics and techniques. 14 tactics with 193 techniques. Used for threat intelligence and detection engineering. Free and regularly updated. Essential framework for defense teams.

### Compliance Standards

- **[PCI-DSS (Payment Card Industry Data Security Standard)](https://www.pcisecuritystandards.org/)** - Security standard for organizations handling credit cards. 12 requirements covering encryption, access control, monitoring. Annual compliance validation required. Levels based on transaction volume. Mandatory for payment processors.

- **[HIPAA (Health Insurance Portability and Accountability Act)](https://www.hhs.gov/hipaa/index.html)** - U.S. regulation protecting patient health information. Security Rule requires safeguards for ePHI. Annual risk assessments required. Severe penalties for violations. Mandatory for healthcare organizations.

- **[GDPR (General Data Protection Regulation)](https://gdpr.eu/)** - European data protection regulation affecting global companies. Strict consent and privacy requirements. Right to erasure and data portability. Heavy fines up to 4% of revenue. Applies to any company processing EU citizen data.

- **[SOC 2](https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/aicpasoc2report.html)** - Auditing standard for security, availability, and confidentiality. Type I (point-in-time) and Type II (period of time). Required by enterprise customers. Demonstrates security controls. Common for SaaS companies.

---

## Contributing

Contributions welcome! Please read the [contribution guidelines](contributing.md) first.

## License

See [LICENSE](LICENSE) file for details.

