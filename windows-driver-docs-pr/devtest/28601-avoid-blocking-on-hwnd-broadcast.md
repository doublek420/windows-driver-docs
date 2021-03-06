---
title: C28601
description: Warning C28601 Avoid blocking on HWND_BROADCAST.
ms.assetid: 51fc27da-012a-4cf3-adbf-bd7f7c497b01
ms.author: windowsdriverdev
ms.date: 04/20/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# C28601


warning C28601: Avoid blocking on HWND\_BROADCAST

This warning indicates that the application called **SendMessage** with the **HWND\_BROADCAST** flag, which blocks the thread until all the windows to which this message was broadcast respond. However, if there is another window that is not responding, the current thread will also be blocked.

To fix this, use **PostMessage** instead, so that it is not a blocking call. Alternatively, avoid the use of **HWND\_BROADCAST** to direct the message to a particular window.

### <span id="example"></span><span id="EXAMPLE"></span>Example

The following call could cause the process to stop responding.

```
SendMessage(HWND_BROADCAST, ... );
```

 

 





