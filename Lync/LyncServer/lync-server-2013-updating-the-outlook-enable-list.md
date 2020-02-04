---
title: 'Lync Server 2013: обновление списка включения Outlook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44de6e3b7756935829b008c585474e08f6f9969
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="07d24-102">Обновление списка включения Outlook в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07d24-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07d24-103">_**Тема последнего изменения:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="07d24-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="07d24-104">Вы можете сделать так, чтобы надстройка сетевого собрания для Microsoft Lync 2013 всегда оставалась включена для пользователей путем создания политики, которая включает ее в список управления надстройками для Outlook.</span><span class="sxs-lookup"><span data-stu-id="07d24-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="07d24-105">Политика списка управления надстройками входит в файлы административных шаблонов Office для консоли управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="07d24-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="07d24-106">Он создает раздел реестра в разделе политики\\\\\\программного обеспечения\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\устойчивость аддинлист.</span><span class="sxs-lookup"><span data-stu-id="07d24-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="07d24-107">Вы можете добавить в этот раздел значение укаддин. dll и настроить значение укаддин. dll так, чтобы оно всегда было включено и не могло вручную его отключить.</span><span class="sxs-lookup"><span data-stu-id="07d24-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="07d24-108">Добавление укаддин. dll в список надстроек для Outlook</span><span class="sxs-lookup"><span data-stu-id="07d24-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="07d24-109">В раздел реестра Аддинлист, который находится в разделе\\политики\\\\программного\\обеспечения\\HKCU\\Microsoft\\Office 15,0\\Outlook15 устойчивость аддинлист, добавьте следующее значение:</span><span class="sxs-lookup"><span data-stu-id="07d24-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="07d24-110">Тип реестра = REG\_СЗ</span><span class="sxs-lookup"><span data-stu-id="07d24-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="07d24-111">Name = укаддин. dll</span><span class="sxs-lookup"><span data-stu-id="07d24-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="07d24-112">Value = 1 (указывает, что надстройка всегда включена и не может управляться конечным пользователем)</span><span class="sxs-lookup"><span data-stu-id="07d24-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

