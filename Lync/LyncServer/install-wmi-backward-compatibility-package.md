---
title: Установка пакета обратной совместимости WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5746077a521bf7dd739e0653a84a4cc7a56b595
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="201c3-102">Установка пакета обратной совместимости WMI</span><span class="sxs-lookup"><span data-stu-id="201c3-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="201c3-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="201c3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="201c3-104">Если попытаться запустить мастер объединения построителя топологий без установки пакета обратной совместимости WMI, появится следующая ошибка.</span><span class="sxs-lookup"><span data-stu-id="201c3-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="201c3-105">![Сообщение об ошибке WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Сообщение об ошибке WMI")</span><span class="sxs-lookup"><span data-stu-id="201c3-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="201c3-106">Если попытаться запустить командлет **Merge-CsLegacytopology** без установки пакета обратной совместимости WMI, появится следующая ошибка.</span><span class="sxs-lookup"><span data-stu-id="201c3-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="201c3-107">![Ошибка поставщика WMI Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Ошибка поставщика WMI Windows PowerShell")</span><span class="sxs-lookup"><span data-stu-id="201c3-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="201c3-108">Чтобы установить пакет обратной совместимости WMI, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="201c3-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="201c3-109">\\На установочном носителе перейдите в раздел Setup\\оксвмибк\\Setup\\. MSI.</span><span class="sxs-lookup"><span data-stu-id="201c3-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="201c3-110">Установите OCSWMIBC.MSI.</span><span class="sxs-lookup"><span data-stu-id="201c3-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="201c3-p101">Пакет OCSWMIBC.msi должен быть установлен на компьютере, где выполняется мастер объединения построителя топологий. Однако рекомендуется устанавливать OCSWMIBC.msi на всех интерфейсных серверах в используемой топологии.</span><span class="sxs-lookup"><span data-stu-id="201c3-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="201c3-113">ОКСВМИБК. msi можно установить на любой компьютер в домене, на котором установлены основные компоненты Lync Server 2013 и Командная консоль Lync Server 2013, и получить доступ к топологии Office Communications Server 2007 R2 (поставщик WMI для домена Active Directory) Services (AD DS) и SQL Server).</span><span class="sxs-lookup"><span data-stu-id="201c3-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

