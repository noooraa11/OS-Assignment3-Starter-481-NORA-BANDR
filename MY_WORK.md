# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [nora bandr albashir ] |
| **Student ID** | [446052003] |
| **University Email** | [446052003@std.psau.edu.sa |
| **GitHub Username** | [@noooraa11] |
| **Repository Link** | [( https://github.com/noooraa11/OS-Assignment3-Starter-481-NORA-BANDR/blob/main/MY_WORK.md )]
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 2 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 3 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 4 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 5 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [15 hours]

**Most challenging part**:Replacing the busy-waiting loops with the semaphore while ensuring proper thread shutdown without deadlocks.

**Most interesting learning**:Seeing how `ReentrantLock` and `Semaphore` directly eliminate race conditions and CPU spinning overhead.

**What I would do differently next time**:Start breaking down the technical reflection questions alongside each coding feature to save time at the end.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[Through this assignment, I gained a deep practical understanding of how critical sections and race conditions affect multi-threaded Java programs. I learned that without mutual exclusion mechanisms like `ReentrantLock`, concurrent threads can interleave their read-modify-write operations, leading to corrupted shared states and unpredictable program behavior. Implementing `try/finally` blocks taught me the importance of guaranteeing that locks are always released safely, even if exceptions arise. Furthermore, replacing active polling with a counting semaphore demonstrated how operating systems manage thread blocking and wake-up efficiency without wasting CPU cycles. Ultimately, this exercise bridged the gap between theoretical operating systems concepts and real-world concurrent programming safeguards ]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part of this assignment was designing the semaphore integration to completely eliminate busy waiting while ensuring that all CPU worker threads terminate cleanly during shutdown. In the original starter code, CPUs continuously polled the ready queue in a tight loop, which wasted system resources. Transitioning to a counting semaphore required carefully tracking when to acquire permits upon dequeueing and when to release permits upon enqueueing processes. Handling the final shutdown signal without leaving worker threads blocked indefinitely in `acquire()` demanded careful condition checks. Balancing this logic alongside fine-grained locks for statistics made concurrency management intricate and required rigorous step-by-step debugging.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I overcame these challenges by adopting a methodical, incremental approach to coding and testing. Whenever I encountered unexpected thread behavior or deadlocks, I reviewed the Chapter 5 lecture notes and re-read the assignment's `README.md` guidelines regarding semaphore initialization and cleanup. I also utilized targeted console print statements to trace thread execution flow and verify when permits were acquired or released. Testing my changes after implementing each individual feature—rather than all at once—helped me isolate errors immediately. Additionally, running the complete simulation multiple times consecutively ensured that the verification block passed reliably across all runs.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization concepts are foundational in any software environment where multiple threads or processes share resources. For instance, in online banking and financial transactions, mutual exclusion locks prevent race conditions when two users or automated services attempt to withdraw funds from the same account simultaneously, ensuring ledger accuracy. Another common application is in ticket reservation or seat-booking systems (such as airlines or cinemas), where semaphores and locks prevent double-booking the same seat when multiple customers try to purchase it at the exact same millisecond. Similarly, print spoolers and message queues use producer-consumer synchronization models to handle print jobs or network packets safely and sequentially without data loss.]

### Optional: What would you like to learn more about?

[Through this assignment, I gained a deep practical understanding of how critical sections and race conditions affect multi-threaded Java programs. I learned that without mutual exclusion mechanisms like `ReentrantLock`, concurrent threads can interleave their read-modify-write operations, leading to corrupted shared states and unpredictable program behavior. Implementing `try/finally` blocks taught me the importance of guaranteeing that locks are always released safely, even if exceptions arise. Furthermore, replacing active polling with a counting semaphore demonstrated how operating systems manage thread blocking and wake-up efficiency without wasting CPU cycles. Ultimately, this exercise bridged the gap between theoretical operating systems concepts and real-world concurrent programming safeguards.]

### Optional: How confident do you feel about synchronization concepts now?

[The most challenging part of this assignment was designing the semaphore integration to completely eliminate busy waiting while ensuring that all CPU worker threads terminate cleanly during shutdown. In the original starter code, CPUs continuously polled the ready queue in a tight loop, which wasted system resources. Transitioning to a counting semaphore required carefully tracking when to acquire permits upon dequeueing and when to release permits upon enqueueing processes. Handling the final shutdown signal without leaving worker threads blocked indefinitely in `acquire()` demanded careful condition checks. Balancing this logic alongside fine-grained locks for statistics made concurrency management intricate and required rigorous step-by-step debugging.]

### Optional: Feedback on the assignment

[I overcame these challenges by adopting a methodical, incremental approach to coding and testing. Whenever I encountered unexpected thread behavior or deadlocks, I reviewed the Chapter 5 lecture notes and re-read the assignment's `README.md` guidelines regarding semaphore initialization and cleanup. I also utilized targeted console print statements to trace thread execution flow and verify when permits were acquired or released. Testing my changes after implementing each individual feature—rather than all at once—helped me isolate errors immediately. Additionally, running the complete simulation multiple times consecutively ensured that the verification block passed reliably across all runs.]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[In the original starter code, a race condition occurs because multiple CPU threads attempt to read and remove processes from the shared ready queue concurrently without mutual exclusion. Specifically, when `ReadyQueue.poll()` executes, a thread reads the queue's head item, pauses via `RaceWindow.pause()`, and then removes it. If CPU-1 and CPU-2 read the same head item during this vulnerable window, both believe they own the process, leading to duplicated processing, incorrect counter increments, or null pointer exceptions. This exact bug happens on real hardware due to non-atomic multi-step operations and OS thread pre-emption, and it is notoriously hard to detect because it depends entirely on non-deterministic thread scheduling interleavings.]


Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
[Paste the verification block of your final version here (all lines ✔)]
```

**Explanation of the timeline:**

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I protected critical sections involving queue modifications and statistics updates using dedicated `ReentrantLock` instances. For lock granularity, I chose to use separate locks for the ready queue versus the statistics counters rather than a single global lock. This fine-grained approach reduces thread contention because a CPU updating execution metrics does not block another CPU from inspecting or modifying the ready queue concurrently. Mutual exclusion is enforced by wrapping critical operations inside `lock.lock()` and putting `lock.unlock()` in `try/finally` blocks. However, because standard `ReentrantLock` defaults to non-fair ordering, threads acquire locks based on availability rather than strict FIFO order, which can theoretically lead to thread starvation if contention is extremely high.]
| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the starter code, busy waiting occurred when idle CPU threads repeatedly looped in a `while` condition checking if the ready queue was empty, wasting massive amounts of CPU processing cycles (evidenced by high poll counts in the starter output). In my final version, the counting semaphore represents the number of available processes currently waiting in the ready queue. Its initial value is set to match the number of initial processes loaded into the queue so that CPUs can immediately acquire permits without blocking unnecessarily. When the queue is empty, CPUs call `semaphore.acquire()`, placing them in a blocked waiting state managed efficiently by the OS kernel rather than consuming CPU time. At the end of the simulation, cleanup routines invoke release calls to unblock waiting threads so they can recognize termination flags and shut down cleanly.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[**Classical problem and roles**: This scenario models the classical **Producer-Consumer problem** (similar to the bounded-buffer problem). Here, scheduler threads or processes acting as producers generate tasks into the ready queue, while the CPU worker threads act as consumers that remove and execute processes.]

**Semaphores for a bounded queue (name and initial value)**:
[1. `empty` (initial value = `K`, representing available slots).
2. `full` (initial value = `0`, representing available items to consume).
3. `mutex` (initial value = `1`, for mutual exclusion over the buffer).]

**Deadlock scenario and prevention**:
[DA deadlock would occur if a CPU thread acquired the mutex lock first and then executed `semaphore.acquire()` while the semaphore count was zero (no processes available), causing it to sleep while holding the mutex. Consequently, producer threads attempting to add new processes would block waiting for the mutex held by the sleeping consumer, creating a permanent circular wait. To prevent this, we break the "Hold and Wait" necessary condition by ensuring that resource locks are released before blocking on synchronization primitives, or by adhering to a strict, globally consistent lock-acquisition order.]
## Summary

**Key concepts I understood through these questions:**
1. How mutual exclusion locks (`ReentrantLock`) prevent race conditions by protecting critical sections with `try/finally` blocks.
2. The operational difference between active polling (busy waiting) and efficient thread suspension using counting semaphores.
3. The importance of fine-grained lock granularity in minimizing thread contention and avoiding deadlocks in multi-threaded environments.

**Concepts I need to study more:**
1. Fair vs. non-fair lock policies in `ReentrantLock` and their impact on thread starvation.
2. Advanced deadlock prevention algorithms and resource-allocation graph analysis.
---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
