## 2.计算机的基本结构

Your computer has a processor chip inside it that does the actual computing. It has internal memory (what DOS/Windows people call "RAM" and Unix people often call "core"; the Unix term is a folk memory from when RAM consisted of ferrite-core donuts). The processor and memory live on the *motherboard*, which is the heart of your computer.

您的计算机内部有一个处理器芯片，可以进行实际计算。它具有内部存储器（DOS/Windows 用户称之为 “RAM”，而 Unix 用户通常称之为“核心”；Unix 术语是 RAM 由铁氧体磁芯甜甜圈组成时的民间存储器）。处理器和内存位于 *主板*上，主板是计算机的心脏。

Your computer has a screen and keyboard. It has hard drives and an optical CD-ROM (or maybe a DVD drive) and maybe a floppy disk. Some of these devices are run by *controller cards* that plug into the motherboard and help the computer drive them; others are run by specialized chipsets directly on the motherboard that fulfill the same function as a controller card. Your keyboard is too simple to need a separate card; the controller is built into the keyboard chassis itself.

您的计算机有屏幕和键盘。它有硬盘驱动器和光 CD-ROM（或者可能是 DVD 驱动器）和软盘。其中一些设备由插入主板并帮助计算机驱动它们的*控制器卡运行；*其他的则由直接在主板上的专用芯片组运行，这些芯片组具有与控制器卡相同的功能。你的键盘太简单了，不需要单独的卡；控制器内置于键盘机箱本身。

We'll go into some of the details of how these devices work later. For now, here are a few basic things to keep in mind about how they work together:

稍后我们将详细介绍这些设备的工作原理。现在，关于它们如何协同工作，请牢记以下一些基本事项：

All the parts of your computer inside the case are connected by a *bus*. Physically, the bus is what you plug your controller cards into (the video card, the disk controller, a sound card if you have one). The bus is the data highway between your processor, your screen, your disk, and everything else.

机箱内计算机的所有部件都通过 *总线*连接。从物理上讲，总线就是您将控制器卡插入的地方（视频卡、磁盘控制器、声卡，如果有的话）。总线是处理器、屏幕、磁盘和其他一切之间的数据高速公路。

(If you've seen references to ‘ISA’, ‘PCI’, and ‘PCMCIA’ in connection with PCs and have not understood them, these are bus types. ISA is, except in minor details, the same bus that was used on IBM's original PCs in 1980; it is no longer used. PCI, for Peripheral Component Interconnection, is the bus used on most modern PCs, and on modern Macintoshes as well. PCMCIA is a variant of ISA with smaller physical connectors used on laptop computers.)

（如果您看到过与 PC 相关的“ISA”、“PCI”和“PCMCIA”参考，但还没有理解它们，那么这些都是总线类型。除了次要细节外，ISA 与 PC 上使用的总线相同。 IBM 于 1980 年推出的原始 PC；它已不再使用。PCI，用于外围组件互连，是大多数现代 PC 和现代 Macintosh 上使用的总线。PCMCIA 是 ISA 的一种变体，具有用于笔记本电脑的更小的物理连接器。 )

The processor, which makes everything else go, can't actually see any of the other pieces directly; it has to talk to them over the bus. The only other subsystem that it has really fast, immediate access to is memory (the core). In order for programs to run, then, they have to be *in core* (in memory).

处理其他一切的处理器实际上无法直接看到任何其他部分；它必须通过总线与他们交谈。它唯一可以快速、立即访问的其他子系统是内存（核心）。那么，为了让程序运行，它们必须*在核心*（在内存中）。

When your computer reads a program or data off the disk, what actually happens is that the processor uses the bus to send a disk read request to your disk controller. Some time later the disk controller uses the bus to signal the processor that it has read the data and put it in a certain location in memory. The processor can then use the bus to look at that data.

当您的计算机从磁盘读取程序或数据时，实际发生的是处理器使用总线向您的磁盘控制器发送磁盘读取请求。一段时间后，磁盘控制器使用总线向处理器发出信号，表明它已读取数据并将其放入内存中的某个位置。然后处理器可以使用总线查看该数据。

Your keyboard and screen also communicate with the processor via the bus, but in simpler ways. We'll discuss those later on. For now, you know enough to understand what happens when you turn on your computer.

您的键盘和屏幕也通过总线与处理器通信，但方式更简单。我们稍后会讨论这些。现在，您已经足够了解打开计算机时会发生什么。

## 3. 当你打开电脑时会发生什么？

A computer without a program running is just an inert hunk of electronics. The first thing a computer has to do when it is turned on is start up a special program called an *operating system*. The operating system's job is to help other computer programs to work by handling the messy details of controlling the computer's hardware.

没有运行程序的计算机只是一堆惰性电子设备。电脑开机后要做的第一件事就是启动一个名为*操作系统*的特定程序。操作系统的工作是通过处理控制计算机硬件的杂乱细节来帮助其他计算机程序工作。

The process of bringing up the operating system is called *booting* (originally this was *bootstrapping* and alluded to the process of pulling yourself up "by your bootstraps"). Your computer knows how to boot because instructions for booting are built into one of its chips, the BIOS (or Basic Input/Output System) chip.

启动操作系统的过程称为 *引导*	`booting`（最初这是 *引导，并暗指*“通过引导”将自己拉起来的过程）。您的计算机知道如何启动，因为启动指令内置于其芯片之一，即 BIOS（或Basic Input/Output System）芯片中。

The BIOS chip tells it to look in a fixed place, usually on the lowest-numbered hard disk (the *boot disk*) for a special program called a *boot loader* (under Linux the boot loader is called Grub or LILO). The boot loader is pulled into memory and started. The boot loader's job is to start the real operating system.

BIOS 芯片告诉它在一个固定的地方查找，通常是在最低编号的硬盘（引导磁盘）上寻找一个称为  *Boot loader*  程序的特殊程序（在 Linux 下，引导加载程序称为 Grub 或 LILO）。引导加载程序被放入内存并启动。引导加载程序的工作是启动真正的操作系统。

The loader does this by looking for a *kernel*, loading it into memory, and starting it. If you Linux and see "LILO" on the screen followed by a bunch of dots, it is loading the kernel. (Each dot means it has loaded another *disk block* of kernel code.)

加载程序通过查找 *内核*、将其加载到内存并启动它来完成此操作。如果你在 Linux 上看到“LILO”在屏幕上后面跟着一串点，那么它正在加载内核。（每个点表示它已加载另一个*内核代码的磁盘块*。）

(You may wonder why the BIOS doesn't load the kernel directly — why the two-step process with the boot loader? Well, the BIOS isn't very smart. In fact it's very stupid, and Linux doesn't use it at all after boot time. It was originally written for primitive 8-bit PCs with tiny disks, and literally can't access enough of the disk to load the kernel directly. The boot loader step also lets you start one of several operating systems off different places on your disk, in the unlikely event that Unix isn't good enough for you.)

（你可能想知道为什么 BIOS 不直接加载内核——为什么要使用 `boot loader` 的两步过程？好吧，BIOS 不是很聪明。事实上它很愚蠢，Linux 在boot time之后根本不会使用它。它最初是为具有微小磁盘的原始 8 位 PC 编写的，并且实际上无法访问足够的磁盘来直接加载内核。引导加载程序步骤还可以让您从放在你的磁盘上的不同的操作系统中启动一个，以防 Unix 对你来说不够好。）

Once the kernel starts, it has to look around, find the rest of the hardware, and get ready to run programs. It does this by poking not at ordinary memory locations but rather at *I/O ports* — special bus addresses that are likely to have device controller cards listening at them for commands. The kernel doesn't poke at random; it has a lot of built-in knowledge about what it's likely to find where, and how controllers will respond if they're present. This process is called *autoprobing*.

一旦内核启动，它必须环顾四周，找到其余的硬件，并准备好运行程序。它不是通过普通内存位置而是通过*I/O 端口* 来实现这一点——特殊的总线地址可能有设备控制器卡在它们上侦听命令。内核不会随意戳；它有很多关于它可能在哪里找到什么以及控制器在出现时将如何响应的内置知识。这个过程称为 *自动探测*。

You may or may not be able to see any of this going on. Back when Unix systems used text consoles, you'd see boot messages scroll by on your screen as the system started up. Nowawadays, Unixes often hide the boot messages behind a graphical splash screen. You may be able to see them by switching to a text console view with the key combination Ctrl-Shift-F1. If this works, you should be able to switch back to the graphical boot screen with a different Ctrl-Shift sequence; try F7, F8, and F9.

您可能会或可能不会看到任何正在发生的事情。当 Unix 系统使用文本控制台时，您会在系统启动时看到引导消息在屏幕上滚动。如今，Unix 经常将引导消息隐藏在图形启动画面后面。您可以通过使用组合键 Ctrl-Shift-F1 切换到文本控制台视图来查看它们。如果可行，您应该能够使用不同的 Ctrl-Shift 顺序切换回图形启动屏幕；尝试 F7、F8 和 F9。

Most of the messages emitted boot time are the kernel autoprobing your hardware through the I/O ports, figuring out what it has available to it and adapting itself to your machine. The Linux kernel is extremely good at this, better than most other Unixes and *much* better than DOS or Windows. In fact, many Linux old-timers think the cleverness of Linux's boot-time probes (which made it relatively easy to install) was a major reason it broke out of the pack of free-Unix experiments to attract a critical mass of users.

启动时发出的大部分消息是内核通过 I/O 端口自动探测您的硬件，找出它可用的内容并适应您的机器。Linux 内核在这方面非常擅长，比大多数其他 Unix 都要好，也比 DOS 或 Windows 好得多*。*事实上，许多 Linux 老手认为 Linux 启动时探测的聪明（这使得它相对容易安装）是它从自由 Unix 实验包中脱颖而出并吸引大量用户的主要原因。

But getting the kernel fully loaded and running isn't the end of the boot process; it's just the first stage (sometimes called *run level 1*). After this first stage, the kernel hands control to a special process called ‘init’ which spawns several housekeeping processes. (Some recent Linuxes use a different program called ‘upstart’ that does similar things)

但是让内核完全加载并运行并不是引导过程的结束；这只是第一阶段（有时称为*运行级别 1*）。在第一阶段之后，内核将控制权交给一个名为“init”的特殊进程，该进程会产生多个内务处理进程。（一些最近的 Linux 使用一个叫做“upstart”的不同程序来做类似的事情）

The init process's first job is usually to check to make sure your disks are OK. Disk file systems are fragile things; if they've been damaged by a hardware failure or a sudden power outage, there are good reasons to take recovery steps before your Unix is all the way up. We'll go into some of this later on when we talk about [how file systems can go wrong](https://tldp.org/HOWTO/Unix-and-Internet-Fundamentals-HOWTO/disk-layout.html#fsck).

init 进程的第一项工作通常是检查以确保您的磁盘正常。磁盘文件系统是脆弱的东西；如果它们因硬件故障或突然断电而损坏，则有充分的理由在您的 Unix 完全启动之前采取恢复步骤。稍后当我们讨论[文件系统如何出错](https://tldp.org/HOWTO/Unix-and-Internet-Fundamentals-HOWTO/disk-layout.html#fsck)时，我们将讨论其中的一些内容。

Init's next step is to start several *daemons*. A daemon is a program like a print spooler, a mail listener or a WWW server that lurks in the background, waiting for things to do. These special programs often have to coordinate several requests that could conflict. They are daemons because it's often easier to write one program that runs constantly and knows about all requests than it would be to try to make sure that a flock of copies (each processing one request and all running at the same time) don't step on each other. The particular collection of daemons your system starts may vary, but will almost always include a print spooler (a gatekeeper daemon for your printer).

Init 的下一步是启动几个*守护进程*。守护进程是一个类似于打印后台处理程序、邮件监听器或 WWW 服务器的程序，它潜伏在后台，等待执行某些操作。这些特殊程序通常必须协调可能发生冲突的多个请求。它们是守护进程，因为编写一个持续运行并了解所有请求的程序通常比尝试确保一组副本（每个副本处理一个请求并同时运行）不会出错要容易得多在彼此身上。您的系统启动的特定守护程序集合可能会有所不同，但几乎总是包含打印后台处理程序（打印机的网守守护程序）。

The next step is to prepare for users. Init starts a copy of a program called **getty** to watch your screen and keyboard (and maybe more copies to watch dial-in serial ports). Actually, nowadays it usually starts multiple copies of **getty** so you have several (usually 7 or 8) virtual consoles, with your screen and keyboards connected to one of them at a time. But you likely won't see any of these, because one of your consoles will be taken over by the X server (about which more in a bit).

下一步是为用户做准备。Init 启动一个名为**getty**的程序的副本来监视您的屏幕和键盘（可能还有更多副本来监视拨入串行端口）。实际上，如今它通常会启动多个**getty**副本，因此您有多个（通常是 7 或 8 个）虚拟控制台，您的屏幕和键盘一次连接到其中一个。但是您可能不会看到其中任何一个，因为您的其中一个控制台将被 X 服务器接管（稍后会详细介绍）。

We're not done yet. The next step is to start up various daemons that support networking and other services. The most important of these is your X server. X is a daemon that manages your display, keyboard, and mouse. Its main job is to produce the color pixel graphics you normally see on your screen.

我们还没有完成。下一步是启动支持网络和其他服务的各种守护进程。其中最重要的是您的 X 服务器。X 是一个管理显示器、键盘和鼠标的守护进程。它的主要工作是生成您通常在屏幕上看到的彩色像素图形。

When the X server comes up, during the last part of your machine's boot process, it effectively takes over the hardware from whatever virtual console was previously in control. That's when you'll see a graphical login screen, produced for you by a program called a *display manager*.

当 X 服务器出现时，在机器启动过程的最后部分，它有效地接管了以前控制的任何虚拟控制台的硬件。那时您将看到一个图形登录屏幕，它是由一个名为*显示管理器*的程序为您生成的。





## 4. 登录后会发生什么？

当您登录时，您向计算机表明了自己的身份。在现代 Unix 上，您通常会通过图形显示管理器来完成此操作。但也可以使用 Ctrl-Shift 键序列切换虚拟控制台并进行文本登录。在那种情况下，您通过 **getty**实例查看该控制台以调用程序**login**。

您向显示管理器表明您自己的身份或 使用**登录**名和密码登录。该登录名在名为 /etc/passwd 的文件中查找，该文件是一系列行，每行描述一个用户帐户。

其中一个字段是帐户密码的加密版本（有时加密字段实际上保存在第二个 /etc/shadow 文件中，具有更严格的权限；这使得密码破解更加困难）。您输入的帐户密码以完全相同的方式加密，**登录**程序会检查它们是否匹配。这种方法的安全性取决于这样一个事实：虽然从明文密码到加密版本很容易，但反过来却非常困难。因此，即使有人可以看到您密码的加密版本，他们也无法使用您的帐户。（这也意味着如果您忘记了密码，则无法恢复它，只能将其更改为您选择的其他内容。）

成功登录后，您将获得与您正在使用的个人帐户相关的所有权限。您也可能被认为是某个 *团体*的一员。组是由系统管理员设置的命名用户集合。组可以拥有独立于其成员特权的特权。一个用户可以是多个组的成员。（有关 Unix 权限如何工作的详细信息，请参阅下面关于[权限](https://tldp.org/HOWTO/Unix-and-Internet-Fundamentals-HOWTO/disk-layout.html#permissions)的部分。）

（请注意，虽然您通常会按名称引用用户和组，但实际上它们在内部存储为数字 ID。密码文件将您的帐户名映射到用户 ID； `/etc/group` 文件将组名映射到数字组 ID。处理帐户和组的命令会自动进行转换。）

您的帐户条目还包含您的*主目录*，这是您的个人文件所在的 Unix 文件系统中的位置。最后，您的帐户条目还设置了您的 *shell*，**登录**将启动的命令解释器接受您的命令。

成功登录后会发生什么取决于您是如何登录的。在文本控制台上，**登录**将启动一个 shell，您将关闭并运行。如果您通过显示管理器登录，X 服务器将打开您的图形桌面，您将能够从中运行程序——通过菜单、通过桌面图标，或者通过运行*shell的**终端仿真器*。



## 5. 开机后运行程序会怎样？

After boot time and before you run a program, you can think of your computer as containing a zoo of processes that are all waiting for something to do. They're all waiting on *events*. An event can be you pressing a key or moving a mouse. Or, **if your machine is hooked to a network**, an event can be a data packet coming in over that network.

在启动时间之后和运行程序之前，您可以将计算机视为包含一个进程动物园，这些进程都在等待执行某些操作。他们都在等待*事件*。事件可以是您按下一个键或移动鼠标。或者，**如果您的机器连接到网络**，则事件可以是通过该网络传入的数据包。

内核是这些进程之一。这是一个特殊的进程，因为它控制着其他*用户进程*何时可以运行，并且它通常是唯一可以直接访问机器硬件的进程。事实上，当用户进程想要获得键盘输入、写入屏幕、读取或写入磁盘，或者除了在内存中处理位之外的任何事情时，都必须向内核发出请求。这些请求称为*系统调用*。

通常所有 I/O 都通过内核，因此它可以安排操作并防止进程相互踩踏。允许一些特殊的用户进程在内核中滑动，通常是通过直接访问 I/O 端口。X 服务器是最常见的例子。

You will run programs in one of two ways: through your X server or through a shell. Often, you'll actually do both, because you'll start a terminal **emulator(仿真器；仿真程序)** that mimics an old-fashioned textual console, giving you a shell to run programs from. I'll describe what happens when you do that, then I'll return to what happens when you run a program through an X menu or desktop icon.

您将以两种方式之一运行程序：通过您的 X 服务器或通过 shell。通常，您实际上会同时执行这两种操作，因为您将启动一个模拟老式文本控制台的终端仿真器，为您提供一个运行程序的 shell。我将描述当您这样做时会发生什么，然后我将返回到当您通过 X 菜单或桌面图标运行程序时会发生什么。

The shell is called the shell because it wraps around and hides the operating system kernel. It's an important feature of Unix that the shell and kernel are separate programs communicating through **a small set of system calls**. This makes it possible for there to be multiple shells, suiting different tastes in interfaces.

外壳之所以称为外壳，是因为它包裹并隐藏了操作系统内核。shell 和内核是独立的程序，通过一小组系统调用进行通信，这是 Unix 的一个重要特征。这使得有多个 shell 成为可能，以适应界面中的不同口味。

The normal shell gives you the ‘$’ prompt that you see after logging in (**unless you've customized it to be something else**). We won't talk about shell syntax and the easy things you can see on the screen here; instead we'll take a look behind the scenes at what's happening from the computer's point of view.

正常的 shell 会在登录后显示“$”提示符（除非您已将其自定义为其他内容）。我们不会讨论 shell 语法和您可以在屏幕上看到的简单内容；相反，我们将从计算机的角度了解幕后发生的事情。

shell只是一个用户进程，并不是特别特殊的进程。它等待您的击键，（通过内核）监听键盘 I/O 端口。当内核看到它们时，它会将它们回显到您的虚拟控制台或 X 终端仿真器。当内核看到“Enter”时，它会将您的文本行传递给 shell。shell 试图将这些击键解释为命令。

假设您键入“ls”并回车以调用 Unix 目录列表器。shell 应用其内置规则来确定您要运行文件 `/bin/ls`中的可执行命令。它进行系统调用，要求内核将 /bin/ls 作为一个新的*子进程*启动，并通过内核授予它访问屏幕和键盘的权限。然后 shell 进入休眠状态，等待 ls 完成。

当**/bin/ls**完成时，它通过发出*退出*系统调用告诉内核它已完成。然后内核唤醒 shell 并告诉它可以继续运行。shell 发出另一个提示并等待另一行输入。

但是，当您的“ls”正在执行时，可能还会发生其他事情（我们必须假设您正在列出一个很长的目录）。例如，您可以切换到另一个虚拟控制台，在那里登录，然后开始一场 Quake 游戏。或者，假设您已连接到 Internet。**/bin/ls**运行时，您的机器可能正在发送或接收邮件 。

当您通过 X 服务器而不是 shell 运行程序时（即，通过从下拉菜单中选择一个应用程序，或双击桌面图标），与您的 X 服务器关联的几个程序中的任何一个都可以表现得像一个 shell 并启动程序。我将在这里掩盖细节，因为它们既可变又不重要。关键点在于 X 服务器与普通 shell 不同，它不会在客户端程序运行时进入睡眠状态——相反，它位于您和客户端之间，将您的鼠标点击和按键操作传递给它并完成它的请求显示器上的点像素。



## 6. 输入设备和中断如何工作？

您的键盘是一种非常简单的输入设备；很简单，因为它生成少量数据的速度非常慢（按照计算机的标准）。当您按下或释放一个键时，该事件会通过键盘电缆发出信号以引发*硬件中断*。

监视此类中断是操作系统的工作。对于每一种可能的中断，都会有一个*中断处理程序*，这是操作系统的一部分，它会隐藏与它们相关的任何数据（比如你的按键/按键释放值），直到它可以被处理。

键盘的中断处理程序实际上所做的是将键值发送到内存底部附近的系统区域。在那里，当操作系统将控制权交给当前应该从键盘读取的任何程序时，它将可供检查。

磁盘或网卡等更复杂的输入设备以类似的方式工作。早些时候，我提到了磁盘控制器使用总线来发出磁盘请求已完成的信号。实际发生的是磁盘引发中断。然后磁盘中断处理程序将检索到的数据复制到内存中，供发出请求的程序稍后使用。

每种中断都有一个相关的*优先级*。低优先级中断（如键盘事件）必须等待高优先级中断（如时钟滴答或磁盘事件）。Unix 旨在为需要快速处理的事件类型提供高优先级，以保持机器的响应顺畅。

在操作系统的启动时消息中，您可能会看到对*IRQ* 号的引用。您可能知道错误配置硬件的一种常见方法是让两个不同的设备尝试使用相同的 IRQ，但不了解确切原因。

这就是答案。IRQ 是“中断请求”的缩写。操作系统需要在启动时知道每个硬件设备将使用哪个编号的中断，因此它可以将适当的处理程序与每个中断相关联。如果两个不同的设备尝试使用相同的 IRQ，中断有时会被分派到错误的处理程序。这通常至少会锁定设备，并且有时会严重混淆操作系统，以至于它会崩溃或崩溃。





 