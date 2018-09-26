---
title: Перемещение каталогов конференций
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перед ликвидацией пула необходимо выполнить следующую процедуру для каждого каталога конференции в устаревшем пуле.
ms.openlocfilehash: 18cbada5833a5160fc1eb81560c56bc9fcff3e2a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028014"
---
# <a name="move-conference-directories"></a><span data-ttu-id="53b5e-103">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="53b5e-103">Move Conference Directories</span></span>

<span data-ttu-id="53b5e-104">Перед ликвидацией пула необходимо выполнить следующую процедуру для каждого каталога конференции в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="53b5e-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="53b5e-105">Перемещение каталога конференции Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="53b5e-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="53b5e-106">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="53b5e-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="53b5e-107">Чтобы получить идентификатор каталогов конференций в вашей организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="53b5e-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
  ```
  Get-CsConferenceDirectory
  ```

    <span data-ttu-id="53b5e-108">Предыдущая команда возвращает все каталоги конференций в организации.</span><span class="sxs-lookup"><span data-stu-id="53b5e-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="53b5e-109">Из-за, можно ограничить результаты в пул списан.</span><span class="sxs-lookup"><span data-stu-id="53b5e-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="53b5e-110">Например если ликвидации пула с pool01.contoso.net полное доменное имя (FQDN), чтобы ограничить возвращаемые данные для каталогов конференций из этого пула используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="53b5e-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
  ```

    <span data-ttu-id="53b5e-111">Эта команда возвращает только каталоги конференций, в которых свойство ServiceID содержит полное доменное имя pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="53b5e-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="53b5e-112">Для перемещения каталогов конференций, выполните следующую команду для каждого каталога конференции в пуле:</span><span class="sxs-lookup"><span data-stu-id="53b5e-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
  ```
  Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
  ```

    <span data-ttu-id="53b5e-113">К примеру перемещение каталога конференции 3, используйте следующую команду, указав в качестве TargetPool Скайп для пула Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="53b5e-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
  ```
  Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
  ```

    <span data-ttu-id="53b5e-114">Если вы хотите переместить все каталоги конференций в пуле, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="53b5e-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
  ```

<span data-ttu-id="53b5e-115">Загрузите [Microsoft Удаление прежних версий и удаление роли сервера](https://go.microsoft.com/fwlink/p/?linkId=246227) для подробные пошаговые инструкции по ликвидация старых пулов.</span><span class="sxs-lookup"><span data-stu-id="53b5e-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="53b5e-116">После перемещения каталогов конференций, может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="53b5e-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="53b5e-117">Как правило, эта ошибка возникает при Скайп оболочки управления Business Server требуется обновленный набор разрешений Active Directory для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="53b5e-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="53b5e-118">Для устранения этой проблемы, закрыть текущий экземпляр консоли, а затем откройте новый экземпляр объекта командной консоли и повторно выполните команду, чтобы переместить каталог конференции.</span><span class="sxs-lookup"><span data-stu-id="53b5e-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

