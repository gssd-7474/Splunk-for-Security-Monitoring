# Hungry Hustle Splunk Security Assessment

## Overview
This project utilizes Splunk to monitor, detect, and respond to simulated security threats targeting the Hungry Hustle online platform. It focuses on investigating a series of security breaches, analyzing their impact, and creating a comprehensive Splunk dashboard to monitor real-time security events. The dataset provided simulates various security incidents, such as unauthorized access, DDoS attacks, SQL injection, XSS attacks, and website downtime.

---

## Tasks

### Task 1: Security Operations Analysis Using Splunk
This task involved investigating security breaches through Splunk queries and log analysis to answer 10 questions, focusing on identifying security vulnerabilities and malicious activities.

#### Key Findings:
1. **Unauthorized Access Attempts**:
   - Identified the top 10 IP addresses with frequent unauthorized access attempts using HTTP 403 errors.
   - Top offender: IP `223.61.120.136` with 2093 attempts.

2. **Country-Based Analysis**:
   - Found that the United States had the highest unauthorized access attempts (417,398), followed by China and Japan.

3. **Leaked Information**:
   - Discovered that an SSH key file (`empe.ppk`) was leaked from Sam Muller's account by an unauthorized user (ramakaka91).

4. **Workplace Conflict Evidence**:
   - Found that Rick shared Steve's sensitive payslip with a personal comment, leading to workplace conflict.

5. **Insider Threat**:
   - Detected that Tom shared the confidential file `burger_recipe.pdf` with a competitor in exchange for Bitcoin.

6. **Exploited Vulnerabilities**:
   - Identified a Cross-Site Scripting (XSS) attack exploiting the checkout page to steal user data.

7. **Performance Issues**:
   - Analyzed network logs to discover Rick's excessive YouTube usage (550 GB data), affecting his performance.

8. **DDoS Attack**:
   - Found that the website experienced a DDoS attack on May 19, 2024, with 50,000 requests in 9 milliseconds, causing server downtime.

9. **Maintenance Downtime**:
   - Calculated that the website was down for 1439.97 minutes (from 10:00 AM, May 25, to 09:59:58 AM, May 26) due to scheduled maintenance.

10. **Popular Food Item**:
    - The most visited product was "Hustlekebab," accessed 104,443 times.

---

### Task 2: Metrics and Visualization
A Splunk dashboard was developed to provide real-time security insights with the following panels:

1. **Unauthorized Access Percentage**:
   - Displays the percentage of unauthorized access attempts against total web traffic using a Single Value display.

2. **Top 10 Accessed Products**:
   - Visualized with a pie chart, showing the most visited food items on the platform.

3. **Suspicious File Transfers**:
   - Highlights Tom’s unauthorized activity, including sending sensitive files to external parties, using a column chart.

4. **Global Distribution of Unauthorized Access Attempts**:
   - A Choropleth Map displaying countries with the highest unauthorized access attempts.

#### Splunk Functions Used:
- **eval**: For calculating unauthorized access percentages.
- **transaction**: To group related events for behavior analysis.
- **Custom Field Extraction**: Using regex (`rex`) to extract filenames and recipients.
- **geom**: For mapping unauthorized access attempts geographically.

---

## Report Component 2: Strategic Security Planning

### Incident Response Plan
To address the recent data breach, a structured **Incident Response Plan** was developed based on the SANS framework:

1. **Preparation**:
   - Establish a dedicated CSIRT team with defined roles.
   - Implement role-based access control (RBAC) and regular employee training.
   - Equip the team with tools like Splunk for monitoring and alerting.

2. **Detection**:
   - Use regular log monitoring and anomaly detection to identify unusual spikes (e.g., DDoS attack).
   - Deploy file integrity monitoring (FIM) to detect unauthorized file changes.

3. **Containment**:
   - Short-term: Block offending IPs, revoke compromised credentials, and disconnect affected systems.
   - Long-term: Implement automated DDoS mitigation and enhance access controls.

4. **Eradication**:
   - Reimage compromised systems to remove malicious artifacts.
   - Patch vulnerabilities, especially the XSS exploit on the checkout page.

5. **Recovery**:
   - Restore systems and monitor activity for 48–72 hours.
   - Validate system performance and ensure no residual threats.

6. **Lessons Learned**:
   - Revise policies to include updated threat vectors.
   - Prepare follow-up reports documenting incident details for future prevention.

---

### Threat Intelligence Recommendations
To enhance Hungry Hustle’s ability to anticipate and mitigate threats, the following Threat Intelligence strategies are proposed:

1. **CTI Integration**:
   - Use platforms like IBM X-Force Exchange for real-time threat intelligence sharing.

2. **Behavioral Analysis**:
   - Employ machine learning to detect anomalies in user behavior, such as unauthorized file transfers.

3. **Actionable Intelligence**:
   - Automate threat detection and response using Splunk’s threat intelligence capabilities.

4. **Vulnerability Management**:
   - Prioritize patching based on CTI insights, focusing on high-risk vulnerabilities like the XSS exploit.

5. **Collaboration**:
   - Join industry-specific threat intelligence networks for shared insights and proactive defense.

---

## Conclusion
By combining thorough log analysis, actionable dashboards, and strategic security planning, this project highlights the importance of proactive and reactive cybersecurity measures. The incident response plan and threat intelligence recommendations will strengthen Hungry Hustle’s defenses, ensuring robust protection against future threats.

**Disclaimer**: This project is for educational purposes and demonstrates Splunk's capabilities in cybersecurity analysis.

