# Douglas Neuroinformatics Platform Documentation
Welcome to the [**Douglas Neuroinformatics Platform (DNP)**](about_the_platform/index.md) documentation.
```{Important}
**Home folder quota: 300 GB**
<br/>Home folders should be used for code, configuration files, and small test files.  
<br/>**All imaging and project data must be stored in shared/project storage locations, _not_ in your home folder.**

**General Rules for system Use:**
<br/>1. Ensure data integrity by not sharing your login credentials.
<br/>2. Choose a low-use machine. The command 'who' lists users, and 'htop' shows system usage.
<br/>3. For bulk data transfers, connect directly to cicss05 to bypass any round-trip data transfers.
<br/>4. Avoid using your '$HOME' folder for data storage. Utilize your project's '/data' folder instead.
<br/>5. Refrain from using 'sudo'. If you're following instructions that need it, its time to ask for help.

```
If you’re **new to the platform**, start with:
- [Getting started](getting_started/index.md) to set up your user account and learn the basics

If you’re an **existing user**, see
-  [Using the system](using_the_system/index.md) for details on access, data, and software
-  [Research methods](research_methods/index.md) for guidance on sharing datasets  
<br/>
```{toctree}
---
maxdepth: 2

caption: Things we know about
---
about_the_platform/index.md
getting_started/index.md
using_the_system/index.md
research_methods/index.md
getting_help/index.md
resources/index.md
terms_of_service/index.md
```
