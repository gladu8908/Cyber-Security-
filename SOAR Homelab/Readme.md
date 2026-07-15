# SOAR Home Lab (n8n) - Blue Team Learning

## Objective
Hands-on SOAR practice for security analyst skills using free/open-source tools.

## Stack
- n8n (Community Edition)
- Docker Desktop
- Optional: Wazuh, TheHive CE
- Test integrations: AbuseIPDB, AlienVault OTX

## Lab Architecture
1. Alert source (webhook/mock SIEM)
2. n8n workflow engine
3. IOC enrichment APIs
4. Notification channel (Discord/Slack/Email)
5. Case/ticket output (optional)

## Playbooks

### 1) IOC Enrichment
**Input:** IP/domain/hash  
**Steps:** normalize -> query TI APIs -> score -> notify  
**Output:** verdict (low/medium/high), JSON evidence

### 2) Phishing Triage (Simulated)
**Input:** suspicious URL/email fields  
**Steps:** extract indicators -> reputation checks -> risk classification  
**Output:** triage result + recommended action

### 3) Alert Deduplication
**Input:** repeated alerts  
**Steps:** group by indicator/time window -> suppress duplicates  
**Output:** one consolidated incident

## Safety
- Use only lab/test data
- Never store real secrets in plain text
- Keep n8n local while learning
- Start with notify-only playbooks

## Evidence / Portfolio
- `/n8n-workflows/*.json`
- `/docs/screenshots/`
- `/playbooks/*.md`

## Roadmap
- Week 1: n8n basics + IOC playbook
- Week 2: phishing + dedup playbooks
- Week 3: SIEM/case integration + tuning
