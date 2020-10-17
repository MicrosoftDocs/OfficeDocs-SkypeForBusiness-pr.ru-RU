---
title: Перемещение каталогов конференций Lync Server 2010 на Lync Server 2013
description: Переместите каталоги конференц-связи Lync Server 2010 в Lync Server 2013.
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
ms.openlocfilehash: 12ac58ac0ab6f1908e7eac3e5824bf2304256632
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571365"
---
# <a name="move-conference-directories"></a><span data-ttu-id="d36cd-103">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="d36cd-103">Move Conference Directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d36cd-104">_**Последнее изменение темы:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="d36cd-104">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="d36cd-105">Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в пуле Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d36cd-105">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="d36cd-106">Перемещение каталога конференций на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d36cd-106">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="d36cd-107">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d36cd-107">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="d36cd-108">Чтобы получить удостоверение каталогов конференций в Организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d36cd-108">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="d36cd-109">Предыдущая команда возвращает все каталоги конференций в Организации.</span><span class="sxs-lookup"><span data-stu-id="d36cd-109">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="d36cd-110">Из-за этого может потребоваться ограничить результаты для пула, который будет списан.</span><span class="sxs-lookup"><span data-stu-id="d36cd-110">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="d36cd-111">Например, при списании пула с полным доменным именем (FQDN) pool01.contoso.net используйте следующую команду, чтобы ограничить возвращаемые данные каталогами конференций из этого пула:</span><span class="sxs-lookup"><span data-stu-id="d36cd-111">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="d36cd-112">Эта команда возвращает только каталоги конференций, в которых свойство ServiceID содержит полное доменное имя pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="d36cd-112">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="d36cd-113">Чтобы переместить каталоги конференций, выполните следующую команду для каждого каталога конференции в пуле:</span><span class="sxs-lookup"><span data-stu-id="d36cd-113">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="d36cd-114">Например, чтобы переместить каталог конференции 3, используйте эту команду, указав пул Lync Server 2013 в качестве TargetPool:</span><span class="sxs-lookup"><span data-stu-id="d36cd-114">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="d36cd-115">Если вы хотите переместить все каталоги конференций в пуле, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="d36cd-115">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="d36cd-116">Ознакомьтесь с документом "удаление Microsoft Lync Server 2010 и удаление ролей сервера" (которые можно скачать [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) ) для получения исчерпывающих пошаговых инструкций по списанию пулов Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="d36cd-116">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="d36cd-117">При перемещении каталогов конференций может возникнуть следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="d36cd-117">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="d36cd-118">Эта ошибка обычно возникает, если для выполнения задачи в командной консоли Lync Server требуется обновленный набор разрешений Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d36cd-118">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="d36cd-119">Чтобы устранить эту проблему, закройте текущий экземпляр командной консоли, а затем откройте новый экземпляр командной консоли и повторно выполните команду, чтобы переместить каталог конференции.</span><span class="sxs-lookup"><span data-stu-id="d36cd-119">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

