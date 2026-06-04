Windows Endpoint Telemetry Lab – Phishing Incident Walkthrough
This repo is me documenting one of the labs I’ve been working on in my Windows environment.
I wanted to see what actually happens on an endpoint when a phishing attempt lands — not in theory, but in real logs, real telemetry, and real behaviour.

Nothing formal here. Just me experimenting, observing, and keeping track of what I found.

🔧 What I Set Up
I built a Windows 10 VM and turned on a bunch of logging features so I could watch the machine react in real time. I enabled:

Security logs

PowerShell Script Block logging

Microsoft Defender logs

IIS logging (for the phishing landing page I hosted)

The idea was simple: make the system as “talkative” as possible so I could trace everything that happened.

🎣 The Phishing Scenario
To trigger some interesting telemetry, I created a small phishing flow:

A fake “Microsoft Security Alert” email

A fake Microsoft login page hosted locally

User clicks → enters details → Windows starts generating logs

The screenshots in /screenshots show exactly what the victim would see.
It’s a simple setup, but enough to get real endpoint activity.

📡 What I Collected
After running the phishing flow, I pulled the logs to see what Windows captured.
This part was honestly the most interesting — watching the machine tell the story of what happened.

I collected:

Event Viewer logs

PowerShell activity

Defender alerts

Network traces

IIS access logs

Everything worth looking at is in /logs.

🔍 What I Learned
Once everything was enabled, Windows gave me a surprisingly detailed picture of the attack.
From this small lab, I was able to:

Rebuild the entire phishing sequence

Spot the exact events triggered by the fake login page

Follow the user’s clicks through telemetry

See how Defender responded

Build a timeline from scratch

This repo is basically my notes and evidence from that process — raw, practical, and hands‑on.

📸 Screenshots
You’ll find a couple of screenshots in /screenshots:

The phishing email

The fake Microsoft login page

They help show what kicked off the whole chain of events.
