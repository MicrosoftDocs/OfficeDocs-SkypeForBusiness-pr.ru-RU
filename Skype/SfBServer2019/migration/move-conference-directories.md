---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перед списанием пула необходимо выполнить описанные ниже действия для каждой из каталогов конференций в пуле старого.
ms.openlocfilehash: cc989e752e69db31f338b493c403b8b8d4c252cc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237739"
---
# <a name="move-conference-directories"></a><span data-ttu-id="ebc31-103">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="ebc31-103">Move Conference Directories</span></span>

<span data-ttu-id="ebc31-104">Перед списанием пула необходимо выполнить описанные ниже действия для каждой из каталогов конференций в пуле старого.</span><span class="sxs-lookup"><span data-stu-id="ebc31-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="ebc31-105">Перемещение каталога конференций в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="ebc31-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="ebc31-106">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ebc31-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="ebc31-107">Чтобы получить удостоверение каталогов конференции в Организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ebc31-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="ebc31-108">Предыдущая команда возвращает все каталоги конференций в Организации.</span><span class="sxs-lookup"><span data-stu-id="ebc31-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="ebc31-109">По этой причине вам может потребоваться ограничить результаты для пула.</span><span class="sxs-lookup"><span data-stu-id="ebc31-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="ebc31-110">Например, если вы собираетесь списать пул с полным доменным именем (FQDN) pool01.contoso.net, используйте эту команду, чтобы ограничить возвращаемые данные каталогам конференций из этого пула.</span><span class="sxs-lookup"><span data-stu-id="ebc31-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="ebc31-111">Эта команда возвращает только каталоги конференций, в которых свойство Сервицеид имеет полное доменное имя (FQDN) pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="ebc31-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="ebc31-112">Чтобы переместить каталоги конференций, выполните для каждой из каталогов конференций в пуле следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ebc31-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="ebc31-113">Например, чтобы переместить каталог конференций 3, используйте эту команду, указав в качестве Таржетпул пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ebc31-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="ebc31-114">Если вы хотите переместить все каталоги конференций в пуле, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="ebc31-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="ebc31-115">Скачайте раздел [Удаление старой версии Microsoft и удалите роли сервера](https://go.microsoft.com/fwlink/p/?linkId=246227) , чтобы получить исчерпывающие пошаговые инструкции по списанию устаревших пулов.</span><span class="sxs-lookup"><span data-stu-id="ebc31-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="ebc31-116">При перемещении каталогов конференций может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="ebc31-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="ebc31-117">Как правило, эта ошибка возникает, когда для выполнения задачи в командной консоли Skype для бизнеса Server требуется обновленный набор разрешений Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ebc31-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="ebc31-118">Чтобы устранить эту проблему, закройте текущий экземпляр интерпретатора команд, а затем откройте новый экземпляр оболочки и повторно выполните команду, чтобы переместить каталог конференций.</span><span class="sxs-lookup"><span data-stu-id="ebc31-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

