### Speaker 1

Thanks, that's where I came across. I'm `<name>`, scholar from McGrory University and University of Dublin. So, here's the cross-summary of our paper: we have tried to introduce a very centralized platform to streamline AI vulnerability reporting, and we also enable anonymous and verifiable disclosures.

 So, in this broad and vastly fast-moving spectrum of AI, LLMs have started to become very advanced, but they also have started, you know, getting critical vulnerabilities that go unreported. And the current disclosure framework is very inefficient, and this fragmented is just everywhere.

 So our goal, uh, while building security was also to bridge the gap between automated notifications and cryptographic anonymity. So, yeah, as I've said, the rise of AI vulnerabilities—rapid LLM developments—have exposed severe under-the-coat security risks.

 So there's, uh, issues related to privacy leakage, jailbreaking attacks, and adversarial misuse of LLM models.

 So the core problem is that security reporting is very highly fragmented right now, and it lacks a standardized framework. So researchers rely on traditional, you know, methods like direct email contacting to the providers, and fast-paced AI research outpaces the security protocols.

 And the result is a lot of inefficiencies in this entire framework, and a lot of the goals are also lost. So, and another result is that there is very little transparency; nobody knows what's, you know, happening, uh, when the conversation is being taken place between the reporter and the model providers.

 So here are the existing disclosure frameworks. So guidance— a lot of guidelines do exist: guidelines by ACL, guidelines by Neural IV and Neural IPS, but operational execution is quite poor.

 So, you know, there are coordinated flaw disclosure frameworks. So, as I said, general guidelines do exist, but again, they lack a centralized tool.

 We have policy interventions by Neural IPS and ACL; they enforce 30-day calls before public release. And corporate platforms also do exist, for example, HackerOne and OpenAI have come out with programs, but they are also isolated CIOs.

 Yeah, here's the gap in current solutions: existing tools focus on benchmarking and isolation rather than connecting stakeholders, for example, researchers and the model providers. And tools like Fuzzy AI isolate benchmarking to the research environment, and there is no unified pipeline connecting researchers, developers, and model providers.

 So, yeah, we introduced SecurityPulse, which is a centralized collaborative report platform which connects stakeholders seamlessly.

 So here's the core philosophy of our platform: SecurityPulse manages to automate disclosures to optimize coordination and privacy. We have verifiable identity without compromising privacy, automated report forwarding directly to providers, and long-term transparency and open-source data analysis.

 Here's the basic system architecture of our platform: we are trying to use, uh, a React-based frontend, and it's a very, you know, lightweight architecture. And we have also a super-based backend which handles authentication, the database, and edge functions that are present in the application.

 And we also use a decent API to send automated emails to the model providers.

 So here are the different stakeholders involved in our platform: one is the researchers and users who report vulnerabilities anonymously or publicly; others are the companies or the model providers who receive automated structured notification of vulnerabilities; and third are the platform admins who maintain and secure data structure and verification integrity. So here's the basic workflow: the user will try to specify details of the target organization, the model that they want to report, and the issue type.

 And then they will attach evidence, which is most likely a PDF, to show what they're trying to claim. And then they will get a receipt from the platform, which is a local JSON receipt, and also an optional cryptographic certificate to include.

 Uh, so here's the organizational mapping and logic, as I've said. The user will try to report an issue through sending a PDF; it will obtain a certificate back from the platform.

 And then both the model providers and the user can themselves verify using our platform that, okay, that person was the one who reported the issue in the platform. Here is the basic notification pipeline: once the user, you know, generates the receipt and the certificate, an automated email directly reaches the organization, uh, and mentions the title of the research, the model that it was targeted, the organization name, the type of the research, and a nicely generated email is being sent to the organization.

 Here's the cryptographic verification part: once the user generates the report and submits, the system will then compute. The system will generate a public and a private key, which will be stored on the local computer of the user, and then it will sign the entire report and the metadata of the report using the private key.

 And then the public key can be shared either with the model organizers or the admins. So that way the verification can be very seamless.

 So, yeah, that's how the verification portal works, which I just explained. The user will just share the public key with the third-party verifiers, and both the user and the third-party verifiers can verify on our platform using the public key.

 So, yeah, I just wanted to share some, uh, light on the value of anonymity. Anonymous submissions are very critical for impartial peer review, because it will reduce bias, and the organizations can focus more on evaluation on the vulnerability and not the researcher.

 And it will also protect researchers, because it can establish priority by timestamps while keeping the identity safe. And the researchers will also have verifiable claims, so it will enable researchers to do discovery for future publications.

 Uh, here are some use cases that our application handles. It can, you know, effectively handle everything from prompt injections, jailbreaks, ethical compromises, pretty much every kind of vulnerability.

 And there's a specific impact on providers: it will enhance the speed of development and transparency. It will, you know, have centralized visibility into recurring vulnerabilities.

 It will measure providers' response times, and it will also guide future defensive strategies. Uh, so what is our future program vision?

 We have also— we have already open-sourced our, you know, entire application. We also plan to, you know, do some trend analysis so we can also report what types of reports are generally reported.

 For example, jailbreaks or prompt injections, so we can perform some data analysis on that as well. So, yeah, finally, there's the vision: secure AI by centralizing vulnerability reporting.

 We enhance the speed of development and the transparency of building trustworthy AI systems. Thank you.

 Any questions are welcome.

### Speaker 2

 Just curiosity, what's the latest from, uh, Canada, on vulnerability and.
