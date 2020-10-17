---
title: 'Lync Server 2013: командлеты регистратора и режиссера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registrar and Director cmdlets
ms:assetid: 327c08ab-7e1e-47c0-b280-a001722c116f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415641(v=OCS.15)
ms:contentKeyID: 48183813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73528a29a88ee2196d9aa1c522b6d6cdb221a9f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536687"
---
# <a name="registrar-and-director-cmdlets-in-lync-server-2013"></a><span data-ttu-id="9e2b7-102">Командлеты регистратора и директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e2b7-102">Registrar and Director cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e2b7-103">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="9e2b7-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="9e2b7-p101">Регистраторы и Директоры используются для проверки подлинности запросов входа и предоставления сведений о доступности и состоянии пользователей. Командлеты Регистратора и Директора позволяют управлять параметрами конфигурации для этих серверов.</span><span class="sxs-lookup"><span data-stu-id="9e2b7-p101">Registrars and Directors are used to authenticate logon requests and to maintain information about user status and availability. The Registrar and Director cmdlets enable you to manage configuration settings for these servers.</span></span>

<div>

## <a name="registrar-and-director-cmdlets"></a><span data-ttu-id="9e2b7-106">Командлеты Регистратора и Директора</span><span class="sxs-lookup"><span data-stu-id="9e2b7-106">Registrar and Director Cmdlets</span></span>

<span data-ttu-id="9e2b7-107">Далее представлен список командлетов, которые напрямую связаны с управлением Регистратором и Директором:</span><span class="sxs-lookup"><span data-stu-id="9e2b7-107">The following is a list of cmdlets that relate directly to managing Registrars and Directors:</span></span>

<span data-ttu-id="9e2b7-108">**Регистраторы и Директоры**</span><span class="sxs-lookup"><span data-stu-id="9e2b7-108">**Registrars and Directors**</span></span>

  - <span></span>  
    <span data-ttu-id="9e2b7-109">[Set — Ксдиректор](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-109">[Set-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9e2b7-110">[Reset — Кспулрегистрарстате](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-110">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9e2b7-111">[Set — Ксрегистрар](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-111">[Set-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9e2b7-112">[Get — CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-112">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9e2b7-113">[New — CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-113">[New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9e2b7-114">[Remove — CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-114">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9e2b7-115">[Set — CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-115">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9e2b7-116">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9e2b7-116">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e2b7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9e2b7-117">See Also</span></span>


[<span data-ttu-id="9e2b7-118">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e2b7-118">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

