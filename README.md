
<img width="1822" height="524" alt="image" src="https://github.com/user-attachments/assets/ec0c2689-7170-4ff0-9f62-b51c8f90d844" />

# Second Vector
> a quiet identity compromise turns into fraud and silent execution...

Organization: Log(N) Pacific <br>
Platform: Microsoft 365 // Entra ID <br>
Investigation Window: `2026-06-11 03:00 UTC`  → `2026-06-11 13:00 UTC` <br>

The full Incident Response Brief can be read [here]()

## Tech Stack 



## IR Brief
**From:** IR Lead // LOG(N) Pacific<br>
**To:** Threat Hunt // On-Shift <br>
**Re:** Incident 87241 // anonymous sign-in on a finance user

Overnight, Microsoft Entra ID Protection raised an incident against a finance user. A sign-in from an anonymous IP address, flagged on `m.smith` and rated **Low**. The night shift triaged it, found nothing they could act on, and left it in the queue.

You are picking it up. Low-severity identity alerts on finance staff are exactly where a patient operator hides. The detection caught **one sign-in**. It did not ask what happened next. That is your job.

This one is cloud. **No malware to reverse, no endpoint to image.** Everything the attacker did, they did through identity, mail, files and cloud services, and every action left a trace in a different table. You will move across the sign-in logs, the mailbox audit, the Graph activity and the mail events, and tie scattered records back to one session.

What we do not yet know:

   **·** Whether the Low rating is right, or whether the machine dismissed a full compromise  
   **·** What the operator did once inside, and what they took  
   **·** What persisted, and whether it still acts with nobody signed in  
   **·** Who else was drawn into the fraud, and how

Start at the incident. **Incident 87241** is what the night shift left you, open it in Defender XDR and read it before you touch the workspace. The Evidence and Response pane names the principal and the flagged sign-in. From there, the rest is in the Sentinel workspace.

Discover the schema yourself with `take 1` or `getschema`, that is part of the work. Some answers are sign-in telemetry, others live in the mailbox audit, the Graph activity and the mail tables. Pivot across them.

Scope tightly. The intrusion window is **11 June 2026, 03:00 to 13:00 UTC**, but some recon reached back into older mail, so widen out when the evidence tells you to. Narrow per stage as you build the timeline.

Work it in three stages. **Triage** the incident and confirm what you are looking at. **Investigate** the session, the recon, the fraud, the persistence and the data taken, in whatever order the evidence pulls you. Then reach a **judgement** the night shift could not: what really happened, how it was hidden, and what you do about it.

Get hunting.

## Defender XDR Incident
![[Screenshot 2026-06-21 at 2.46.45 PM.png]]
