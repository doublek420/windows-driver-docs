---
title: SignalEventInCompletion rule (wdm)
description: The SignalEventInCompletion rule specifies that when processing an asynchronous IRP, the driver needs to call the KeSetEvent in the completion routine when the Irp- PendingReturned flag is set.
ms.assetid: CF79EB38-82B0-4CD5-B629-8B8D84EB60CA
ms.author: windowsdriverdev
ms.date: 5/21/2018
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
keywords: ["SignalEventInCompletion rule (wdm)"]
topic_type:
- apiref
api_name:
- SignalEventInCompletion
api_type:
- NA
---

# SignalEventInCompletion rule (wdm)


The **SignalEventInCompletion** rule specifies that when processing an asynchronous IRP, the driver needs to call the [**KeSetEvent**](https://msdn.microsoft.com/library/windows/hardware/ff553253) in the completion routine when the **Irp-&gt;PendingReturned** flag is set.

In this case, the completion routine will not be called.

|              |     |
|--------------|-----|
| Driver model | WDM |

How to test
-----------

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">At compile time</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Run [Static Driver Verifier](https://msdn.microsoft.com/library/windows/hardware/ff552808) and specify the <strong>SignalEventInCompletion</strong> rule.</p>
Use the following steps to run an analysis of your code:
<ol>
<li>[Prepare your code (use role type declarations).](https://msdn.microsoft.com/library/windows/hardware/hh454281#preparing-your-source-code)</li>
<li>[Run Static Driver Verifier.](https://msdn.microsoft.com/library/windows/hardware/hh454281#running-static-driver-verifier)</li>
<li>[View and analyze the results.](https://msdn.microsoft.com/library/windows/hardware/hh454281#viewing-and-analyzing-the-results)</li>
</ol>
<p>For more information, see [Using Static Driver Verifier to Find Defects in Drivers](https://msdn.microsoft.com/library/windows/hardware/hh454281).</p></td>
</tr>
</tbody>
</table>

Applies to
----------

[**IoBuildDeviceIoControlRequest**](https://msdn.microsoft.com/library/windows/hardware/ff548318)
[**IoBuildSynchronousFsdRequest**](https://msdn.microsoft.com/library/windows/hardware/ff548330)
[**IoSetCompletionRoutine**](https://msdn.microsoft.com/library/windows/hardware/ff549679)
[**IoSetCompletionRoutineEx**](https://msdn.microsoft.com/library/windows/hardware/ff549686)
[**KeInitializeEvent**](https://msdn.microsoft.com/library/windows/hardware/ff552137)
[**KeSetEvent**](https://msdn.microsoft.com/library/windows/hardware/ff553253)
 

 





