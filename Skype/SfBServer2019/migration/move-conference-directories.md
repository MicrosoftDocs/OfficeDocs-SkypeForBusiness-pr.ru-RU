---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в устаревшем пуле.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752501"
---
# <a name="move-conference-directories"></a><span data-ttu-id="dd690-103">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="dd690-103">Move Conference Directories</span></span>

<span data-ttu-id="dd690-104">Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="dd690-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="dd690-105">Перемещение каталога конференций в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="dd690-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="dd690-106">Откройте оболочку управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dd690-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="dd690-107">Чтобы получить идентификатор каталогов конференций в организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dd690-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="dd690-108">В предыдущей команде возвращаются все каталоги конференций в организации.</span><span class="sxs-lookup"><span data-stu-id="dd690-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="dd690-109">По этой причине может потребоваться ограничить результаты списанием пула.</span><span class="sxs-lookup"><span data-stu-id="dd690-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="dd690-110">Например, если списание пула с использованием полного доменного имени (FQDN) pool01.contoso.net, используйте эту команду, чтобы ограничить возвращаемую информацию каталогами конференций из этого пула:</span><span class="sxs-lookup"><span data-stu-id="dd690-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="dd690-111">Эта команда возвращает только каталоги конференций, свойство ServiceID которых содержит pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="dd690-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="dd690-112">Чтобы переместить каталоги конференций, запустите следующую команду для каждого каталога конференции в пуле:</span><span class="sxs-lookup"><span data-stu-id="dd690-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="dd690-113">Например, чтобы переместить каталог конференции 3, используйте эту команду, указав пул Skype для бизнеса Server 2019 в качестве TargetPool:</span><span class="sxs-lookup"><span data-stu-id="dd690-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="dd690-114">Чтобы переместить все каталоги конференций в пул, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="dd690-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="dd690-115">Скачайте [удаление устаревших](https://go.microsoft.com/fwlink/p/?linkId=246227) ролей Майкрософт и удаление ролей сервера для комплексных пошаговой инструкций по выводу устаревших пулов из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="dd690-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="dd690-116">При перемещении каталогов конференций может возникнуть следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="dd690-116">When moving conference directories, you might encounter the following error:</span></span>
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="dd690-117">Эта ошибка обычно возникает, когда для выполнения задачи в оболочке управления Skype для бизнеса Server требуется обновленный набор разрешений Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dd690-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="dd690-118">Чтобы устранить проблему, закроем текущий экземпляр командной оболочки, а затем откройте новый экземпляр оболочки и повторно запустите команду для перемещения каталога конференции.</span><span class="sxs-lookup"><span data-stu-id="dd690-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

