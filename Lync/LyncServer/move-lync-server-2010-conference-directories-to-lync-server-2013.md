---
title: Перемещение каталогов конференций Lync Server 2010 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9bd597665f389c814fbdc8fe1745587fd3d1b3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="ed238-102">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="ed238-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed238-103">_**Тема последнего изменения:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="ed238-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="ed238-104">Перед списанием пула необходимо выполнить описанные ниже действия для каждой из каталогов конференций в пуле Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ed238-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="ed238-105">Перемещение каталога конференций на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed238-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="ed238-106">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ed238-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ed238-107">Чтобы получить удостоверение каталогов конференции в Организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ed238-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="ed238-108">Предыдущая команда возвращает все каталоги конференций в Организации.</span><span class="sxs-lookup"><span data-stu-id="ed238-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="ed238-109">По этой причине вам может потребоваться ограничить результаты для пула.</span><span class="sxs-lookup"><span data-stu-id="ed238-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="ed238-110">Например, если вы собираетесь списать пул с полным доменным именем (FQDN) pool01.contoso.net, используйте эту команду, чтобы ограничить возвращаемые данные каталогам конференций из этого пула.</span><span class="sxs-lookup"><span data-stu-id="ed238-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="ed238-111">Эта команда возвращает только каталоги конференций, в которых свойство Сервицеид имеет полное доменное имя (FQDN) pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="ed238-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="ed238-112">Чтобы переместить каталоги конференций, выполните для каждой из каталогов конференций в пуле следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ed238-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="ed238-113">Например, чтобы переместить каталог конференции 3, используйте эту команду, указав в качестве Таржетпул пул Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ed238-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="ed238-114">Если вы хотите переместить все каталоги конференций в пуле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ed238-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="ed238-115">Ознакомьтесь со статьей "удаление Microsoft Lync Server 2010 и отключение серверных ролей" (которую можно скачать из [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) для получения подробных пошаговых инструкций по списанию пулов Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ed238-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="ed238-116">При перемещении каталогов конференций может возникнуть следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="ed238-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="ed238-117">Как правило, эта ошибка возникает, когда для выполнения задачи в командной консоли Lync Server Management Shell требуется обновленный набор разрешений Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ed238-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="ed238-118">Чтобы устранить эту проблему, закройте текущий экземпляр интерпретатора команд, а затем откройте новый экземпляр оболочки и повторно выполните команду, чтобы переместить каталог конференций.</span><span class="sxs-lookup"><span data-stu-id="ed238-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

