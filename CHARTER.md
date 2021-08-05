# Safety Task Group charter proposal

## Purpose

The goal of the Safety SIG (special interest group) within the RISC-V Foundation is to identify
the need for various architectural principles and hardware interfaces for achieving Functional
Safety in the RISC-V architecture. Focused task groups will be proposed to the RISC-V
Foundation technical committee to be spun off when sufficient critical mass and discussion
depth is reached on a specific topic.

Functional safety is aimed at controlling and minimizing the risk of systems catastrophic failures
(i.e. failures that can injure or damage people’s health, equipment or the environment). In the
context of software-driven applications, meeting functional safety requires that functional and
timing correctness of applications is guaranteed throughout the system lifetime. Adequate
assurance can rest on robust data collected during the process. The Safety SIG will investigate
and provide guidelines on how to make RISC-V based products amenable for safety-critical
applications. Special focus will be put on how to test and diagnose safety mechanism
effectiveness for relevant fault models (on-line and off-line), how to effectively measure and
improve system robustness for RISC-V based products, mechanisms to ensure isolation
between different components, and the required hardware and software support to achieve
safety properties in an effective manner while providing a simple diagnostic interface to
hypervisor/OS and safety-application developers.

One of the tasks of this SIG will investigate how to guarantee a bounded Worst Case Execution
Time (WCET) that is crucial in most safety-critical applications, both in single and multi-core
architectures. This allows hypervisors and operating systems to guarantee a bounded WCET to
the applications with margins as small as possible.

Special attention must be paid to multi-core processors since the concurrent execution of
threads can create contention during access to various shared resources. Other hardware
mechanisms, such as cache eviction also create execution delays from one thread to another.
I/O devices can delay access to the memory from the main cores.

In general-purpose processors, the WCET contains the sum of all possible interferences.
Interferences from other cores must be kept to a reasonable bound, in order to prevent that the
additional interference from multi-core operation increases the WCET such that there is only
little performance benefit relative to the single-core use. In special-purpose processors, safety
critical applications may be disciplined to efficiently share the resources, but even in this case
additional margins may be required to work around undocumented behavior in the hardware.
When considering a mix of safety critical applications and regular applications, the margin
needs to be greatly increased.

Additional hardware support for efficient switching between tasks (or time partitions) in the OS /
hypervisor may help reduce the margin required to guarantee WCET.

The interfaces shall permit to:

- Provide the ability to maximally decouple cores,
- Guarantee bounded execution time when a core is using a shared resource,
- Prevent external devices from hindering the access to a shared resource,
- Provide direct hardware access from virtualized application to increase performance,
- Communicate between cores with minimized interferences,
- Allow the configuration of the policies executed directly by the hardware (Cache management strategy, TLB, etc.),
- Validate and monitor timing behaviour

In addition to interfaces, the SIG shall provide guidelines on features to be provided by a Safety
Critical RISC-V processor such as independent safety islands, lock-step redundant cores,
watchdog, ECC protected memory or datapaths, etc. Similarly, the SIG will also provide
guidelines on how open-source projects can be made amenable for qualification.

## Participants

Safety SIG expects participation from actors in the safety domain:

- Verticals: automotive, aerospace, space, medical, energy, railway…
- IC providers
- RISC-V and IP block providers and open-source contributors
- OS / Hypervisors providers and open-source contributors
- Technology, tools and service providers
- Academics, researchers, experts…

## Operations

Safety SIG will work under the supervision of the RISC-V Foundation Technical Committee.

Due to the interdisciplinary nature of safety, the SIG can cooperate with other RISC-V
Foundations groups and external organizations following the Foundation bylaws.

The SIG will meet via conference calls or web conferences at a frequency required to sustain
the activity. The SIG can also gather face-to-face at events organized by the Foundation.

The group will use the sig-safety@lists.riscv.org mailing list. Document repository to define.

The group’s business and proceedings will be conducted in English.
