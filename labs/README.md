<div align="center">

## 🧪 CyberX Labs

Hands-on labs you work through in your own VMs — organized so you always know where to start.

<a href="#-how-these-are-organized">How These Are Organized</a> ·
<a href="#-before-you-start">Before You Start</a> ·
<a href="#-keep-it-in-the-lab">Keep It in the Lab</a>

</div>

---

Reading about an attack and running one yourself are two different kinds of knowing. These labs are the second kind. Each one walks you through a technique end to end in a safe, self-contained environment — so whether you're scanning your first host or building your first detection, you learn it by doing it.

Work at your own pace. Break things, roll back your snapshot, and try again. That's what the lab is for.

<a id="-how-these-are-organized"></a>
## 📂 How These Are Organized

Labs are grouped by difficulty so you always know what to reach for next.

| Section | What's there |
|---|---|
| [beginner/](beginner/README.md) | Foundations: VM setup, scanning and enumeration, basic defense, and how credentials get compromised |
| [intermediate/](intermediate/README.md) | Multi-step attack/defense chains, log analysis, and introductory SIEM work |
| [advanced/](advanced/README.md) | Red-team scenarios, detection engineering, and sandboxed malware analysis |

> [!TIP]
> New here? Start with [beginner/](beginner/README.md) and work the labs in order — each one assumes you're comfortable with the one before it.

<a id="-before-you-start"></a>
## 🖥️ Before You Start

Most labs assume a small, isolated lab network with two virtual machines on it:

- an **Ubuntu VM** (your target), and
- a **Kali Linux VM** (your attacker).

If you don't have those running yet, [start-here/](../start-here/README.md) walks through VM setup from zero. Take a snapshot right after first boot so you can always roll back.

<a id="-keep-it-in-the-lab"></a>
## 🔒 Keep It in the Lab

Everything here is meant for machines you own and control, on a network you've isolated. These skills exist so you can defend systems and understand how attackers think — never to touch systems you don't have explicit permission to test. Keep it in the lab.

> [!NOTE]
> Got a lab you want to add — especially for the intermediate or advanced sections? Bring it to the e-board. See [CONTRIBUTING.md](../CONTRIBUTING.md): proposal first, code second.

---

<div align="center">

**Secure the Future, Defend Today!**

[Instagram](https://instagram.com/cyberxcollective) · [Back to cyberx-collective](../README.md)

</div>
