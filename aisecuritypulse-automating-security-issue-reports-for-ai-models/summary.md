Presentation of SecurityPulse, a centralized platform for AI vulnerability disclosure with anonymous, cryptographically verifiable reporting and automated notifications to model providers. Ended with a Q&A prompt.

### Problem & Landscape
- LLM vulnerabilities (privacy leaks, jailbreaks, adversarial misuse) rising but disclosure is fragmented and untransparent
- Existing guidance (ACL, NeurIPS 30-day rule, HackerOne, OpenAI) exists but is siloed with no unified researcher–provider pipeline

### SecurityPulse Platform
- Centralized reporting with anonymous submissions, automated provider emails, and open-source trend analysis
- React frontend, Supabase backend (auth, DB, edge functions), Resend-like API for automated emails
    - Stakeholders: researchers, model providers, platform admins
- Workflow: user submits target org/model/issue + PDF evidence, receives JSON receipt and optional cryptographic certificate
- Crypto verification: local keypair signs report; public key shared with providers/admins for verification via portal

### Value & Roadmap
- Anonymity reduces bias, protects researchers, preserves priority via timestamps, enables verifiable claims for future publication
- Already open-sourced; plans for trend analysis on vulnerability types (jailbreaks, prompt injections, etc.)