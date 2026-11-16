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
| **Full Name** | [Leena saud Alsaif] |
| **Student ID** | [445052525] |
| **University Email** | [445052525]@std.psau.edu.sa |
| **GitHub Username** | [Leena-saud17] |
| **Repository Link** | [https://github.com/Leenaa179/OS-Assignment3-Leena-Alsaif] |
 
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

### Entry 1 - [November 14, 2026, 1:00 PM]
**What I did**: Started working on the assignment by setting up the project and updating my student ID

**Details**:  Forked the repository, opened SchedulerSimulationSync.java, updated my student ID (445052525) on line 304, and ran the original starter code to examine the initial behavior

**Challenges**: The starter code crashed and got stuck due to race conditions and CPU threads picking the same process simultaneously

**Solution**: Solution: Saved the initial output log for documentation and analyzed how ReadyQueue.poll() handles threads without synchronization

**Time spent**:45 minutes

---

### Entry 2 - [November 14, 2026, 2:15 PM]
**What I did**: Implemented the first core feature to protect the ready queue

**Details**: Added a ReentrantLock named queueLock inside ReadyQueue and secured the critical sections in add(), poll(), remove(), and snapshot() using try-finally blocks

**Challenges**: Making sure that every lock acquisition had a guaranteed unlock to prevent any risk of deadlocks

**Solution**: Placed queueLock.unlock() strictly inside the finally block of each method

**Time spent**:1.5 hours

---

### Entry 3 - [November 14, 2026, 4:00 PM]
**What I did**: Secured the shared statistics counters as part of Feature 2

**Details**: Applied fine-grained locking mechanisms to SharedStats to protect the independent statistical variables from race conditions during concurrent updates

**Challenges**: Deciding whether to use a single global lock or separate locks for the different counters

**Solution**: Chose separate locks for independent statistics to minimize thread contention and allow smoother concurrent execution

**Time spent**: 1 hour

---

### Entry 4 - [November 14, 2026, 5:30 PM]
**What I did**: Replaced the busy-waiting mechanism with a counting semaphore for Feature 3

**Details**: Declared a readySemaphore, integrated acquireProcess() in the CpuWorker thread loop, and implemented releaseAllCPUs() to handle clean shutdowns

**Challenges**: Handling CPU thread termination properly so they wouldn't hang indefinitely when all processes finished

**Solution**: Used semaphore permits to block worker threads efficiently at the OS level and released all CPUs upon completion

**Time spent**: 50 minutes

---

### Entry 5 - [November 14, 2026, 7:45 PM]
**What I did**: Finalized testing, verified outputs, and prepared the documentation

**Details**: Ran the program multiple times to ensure all verification checks passed successfully with ✔ marks and Busy-waiting polls reached 0. Completed the reflection and technical questions

**Challenges**: Structuring the technical explanations clearly and connecting them directly to my own code behavior

**Solution**: Reviewed code methods and output logs to write precise, concrete explanations

**Time spent**: 1 hour

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

**Total time spent on assignment**: [5 hours]

**Most challenging part**: Managing the transition from busy-waiting to a counting semaphore in Feature 3, and ensuring that all CPU worker threads terminate cleanly without hanging or leaving dangling threads at the end of the simulation

**Most interesting learning**: Discovering how critical sections and race conditions can completely break multi-threaded program execution, and how using appropriate synchronization primitives like ReentrantLock and counting semaphores restores data integrity and drastically reduces CPU overhead

**What I would do differently next time**: I would write and test each feature incrementally with small trace logs right from the beginning to catch synchronization overlaps even faster

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

[I learned that concurrent threads accessing shared mutable state without synchronization lead to unpredictable race conditions, lost updates, and corrupted data. By implementing mutual exclusion primitives like ReentrantLock with try-finally blocks, we can safely protect critical sections and ensure thread safety. I also realized how counting semaphores help manage resource availability efficiently and eliminate continuous, wasteful CPU polling. Seeing how the original starter code failed with incorrect counters made these theoretical operating systems concepts extremely clear and practical]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part of this assignment was designing Feature 3 and ensuring that all CPU worker threads would terminate cleanly without hanging or leaving dangling threads at the end of the simulation. Managing the initial value of the counting semaphore, replacing the busy-waiting loops, and figuring out the exact logic for releaseAllCPUs() during the final shutdown required careful coordination across ReadyQueue and CpuWorker]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I overcame these challenges by systematically debugging the code, adding trace statements, and re-reading the project instructions and textbook chapters on synchronization. Testing the application incrementally after each small modification allowed me to isolate errors quickly. Whenever I hit a roadblock with thread coordination or lock placement, I reviewed how locks and semaphores interact within critical sections]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization concepts are crucial in real-world applications such as database management systems, multi-threaded web servers, and banking transaction systems where multiple users or processes access shared accounts concurrently. For instance, an online ticket booking system uses mutual exclusion locks to prevent two users from booking the exact same seat simultaneously. Similarly, print queues rely on semaphores to manage print jobs safely in the correct order]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

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

[In the original starter code, race conditions occur because multiple CPU threads read, modify, and write shared variables concurrently without synchronization. A lost update happens when CPU-1 reads a counter value (e.g., 5), CPU-2 reads the same value (5), CPU-1 increments and writes back 6, and then CPU-2 writes back 6, causing one increment to be completely lost. This bug happens on real machines due to interleaved CPU scheduling and is difficult to detect because it occurs non-deterministically.]

Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
[Paste the verification block of your final version here (all lines ✔)]
```

**Explanation of the timeline:**
[Explain the lost update step by step.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[We protected critical sections in ReadyQueue (such as add, poll, remove, and snapshot) using queueLock, and statistics updates in SharedStats using dedicated locks. We used fine-grained locking (separate locks) rather than a single global lock to minimize contention and allow unrelated counters to update concurrently. The ready queue is protected by a separate lock because queue operations do not depend on statistics variables. Mutual exclusion is achieved via ReentrantLock, though default locks are non-fair, meaning threads acquire the lock based on scheduling rather than strict FIFO order]

| Critical section (variable / method) | Lock used | Why it needs protection |
|ReadyQueue (list and map access in add/poll)|queueLock|Prevents concurrent structural modifications and race conditions during queue operations|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [SharedStats counters] | [Dedicated Locks] | [Protects independent statistical variables from lost updates during simultaneous updates by multiple CPUs] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[The starter code used busy-waiting where CpuWorker threads continuously polled the queue in a while loop, resulting in a high number of Busy-waiting polls and wasting massive CPU cycles. In contrast, our final version uses a counting semaphore initialized to 0, representing available processes in the ready queue. Threads call acquireProcess(), which suspends them efficiently at the OS level without wasting CPU time. At the end of the simulation, the last CPU calls releaseAllCPUs(totalCPUs) to wake up any remaining sleeping threads so they can exit cleanly]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[This resembles the classic Producer-Consumer problem (bounded-buffer), where CPUs act as both consumers (taking processes from the ready queue) and producers (re-enqueuing unfinished processes)]

**Semaphores for a bounded queue (name and initial value)**:
[If the queue were bounded, we would need three semaphores: empty (initially K), full (initially 0), and a mutex (initially 1)]

**Deadlock scenario and prevention**:
[A deadlock scenario could occur if a worker thread acquired the mutex lock before waiting on a semaphore for an empty slot, causing other threads to wait indefinitely. To prevent this, we break the "hold and wait" condition by ensuring locks and semaphores are acquired in a strict, safe order]

## Summary

**Key concepts I understood through these questions:**
1.Mutual Exclusion: Preventing race conditions and lost updates on shared data using ReentrantLock with try-finally blocks
2.Semaphores over Busy-Waiting: Using a counting semaphore to block idle CPU threads efficiently instead of wasting CPU cycles in polling loops
3.Lock Granularity & Deadlock Prevention: Using separate locks for independent resources (ReadyQueue vs. SharedStats) to boost concurrency and acquiring locks safely to avoid deadlocks

**Concepts I need to study more:**
1.Fair vs. Non-Fair Locks: Understanding performance and starvation trade-offs in ReentrantLock
2.Java Concurrency Utilities: Exploring ReadWriteLock, Condition variables, and atomic classes like AtomicInteger

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
