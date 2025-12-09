# Securinets ISET Zaghouan x D6ath E9ters CTF - Reverse Engineering Challenges

**Author:** SD0 (Mankaiahmeddhia)

These are the complete writeups for the reverse engineering challenges I created for the **Securinets ISET Zaghouan x D6ath E9ters CTF**. Each challenge was designed with a specific learning objective in mind, forming a progressive journey from basic debugging to advanced techniques like SMT solving and VM reversal.

📝 **Read the full creator's perspective:** [My Journey Authoring Reverse Engineering CTF Challenges](https://medium.com/@mankaiahmeddhia50/my-journey-authoring-reverse-engineering-ctf-challenges-eafe99229ecf)

---

## 🎯 Challenge Overview

| Challenge | Difficulty | Points | Key Concepts | Writeup |
|-----------|-----------|---------|--------------|---------|
| **fast** | Easy | 100 | GDB basics, breakpoints, timing analysis | [📖 Writeup](./Fast/writeup.md) |
| **random** | Easy | 100 | Register inspection, runtime values, dynamic analysis | [📖 Writeup](./Random/writeup.md) |
| **Grandma's Security System** | Medium-Hard | 300 | Multi-layer VMs, strcmp bypass, hash bypass | [📖 Writeup](./Game/writeup.md) |
| **Grandma's Hash Fortress** | Hard | 500 | String extraction, targeted brute force, info gathering | [📖 Writeup](./Hash/writeup.md) |
| **SMT Hell** | Medium | 300 | Z3 solver, constraint extraction, automated reasoning | [📖 Writeup](./smt-hell/writeup.md) |

---

## 🎓 Learning Path

The challenges are designed to form a natural learning progression:

### 1. **fast** - Baby Steps
*Introduction to disassemblers and breakpoints*

Learn to use GDB to pause program execution and control timing-based challenges. Perfect for understanding debugger fundamentals.

### 2. **random** - Reading the CPU's Mind
*Following static logic and reading runtime values*

Discover that you don't need to predict random numbers — you can just read them from registers during execution.

### 3. **Grandma's Security System** - VM Layers
*Multi-layer challenge with progressive difficulty*

Progress through four increasingly complex security layers, from simple string comparison to VM hash bypass. Teaches layer-by-layer analysis and runtime manipulation.

### 4. **SMT Hell** - Automated Constraint Solving
*Introduction to Z3 and SMT solvers*

Face complex, intertwined constraints that are impractical to solve manually. Learn when and how to use automated solvers like Z3.

### 5. **Grandma's Hash Fortress** - Information > Brute Force
*Strategic analysis and targeted attacks*

Extract hidden string pieces from binaries and use strategic brute forcing only for unknown gaps. Resist the urge to "break MD5" and focus on information gathering.

---

## 🛠️ Tools You'll Learn

- **GDB** - GNU Debugger for runtime analysis
- **Ghidra/IDA Pro** - Static analysis and decompilation
- **strings** - Quick reconnaissance
- **Python + hashlib** - Brute force scripting
- **Z3 Solver** - Constraint satisfaction
- **Memory manipulation** - Register and memory patching

---

## 💡 Philosophy

These challenges embody several core reverse engineering principles:

1. **Start Simple** - Always check the easy stuff first (`strings`, basic analysis)
2. **Observe Before Breaking** - Use debuggers to understand before attacking
3. **Layer by Layer** - Complex systems become manageable when broken down
4. **Smart Over Strong** - Bypass cryptography instead of breaking it when possible
5. **Automate Wisely** - Use tools like Z3 when manual analysis becomes impractical

---

## 📂 Repository Structure

```
ctf-writeup/
├── Fast/
│   ├── writeup.md          # Complete walkthrough
│   ├── fast                # Challenge binary
│   └── images/             # Screenshots with context
├── Random/
│   ├── writeup.md
│   ├── random              # Challenge binary
│   └── images/
├── Game/                   # Grandma's Security System
│   ├── writeup.md
│   ├── game                # Challenge binary
│   └── images/             # Layer-by-layer screenshots
├── Hash/                   # Grandma's Hash Fortress
│   ├── writeup.md
│   ├── hash                # Challenge binary
│   └── images/
└── smt-hell/
    ├── writeup.md
    ├── NumberVerifier.class
    └── images/
```

---

## 🚀 Getting Started

1. **Clone this repository**
   ```bash
   git clone https://github.com/Dhia-M/ctf-writeup.git
   cd ctf-writeup
   ```

2. **Choose your challenge** based on skill level (start with `fast` if you're new!)

3. **Try solving it yourself first** before reading the writeup

4. **Learn the techniques** - each writeup includes educational objectives and key takeaways

---

## 🎯 About the CTF

The **Securinets ISET Zaghouan x D6ath E9ters CTF** was designed to provide a learning journey for reverse engineers at all skill levels. These challenges were playtested and refined to ensure each one teaches specific, transferable skills.

### Creator's Notes
Creating these challenges taught me more than solving them ever could. Each puzzle was designed with a specific "aha!" moment in mind — that instant when a player realizes they've been thinking about the problem wrong, and the elegant solution reveals itself.

---

## 📖 Further Reading

- [Medium Article - My Journey Authoring RE Challenges](https://medium.com/@mankaiahmeddhia50/my-journey-authoring-reverse-engineering-ctf-challenges-eafe99229ecf)
- Each challenge writeup includes detailed learning objectives and creator's notes

---

## 📧 Contact

**Author:** Mankaiahmeddhia (SD0)  
**Medium:** [@mankaiahmeddhia50](https://medium.com/@mankaiahmeddhia50)

---

*"Every complex reverse engineering problem is just a series of simple insights waiting to be discovered."*
