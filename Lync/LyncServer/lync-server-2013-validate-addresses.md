---
title: 'Lync Server 2013: Проверка адресов'
description: 'Lync Server 2013: Проверка адресов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547275"
---
# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="7e75e-103">Проверка адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e75e-103">Validate addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e75e-104">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="7e75e-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="7e75e-105">Перед публикацией базы данных местонахождений нужно проверить новые местонахождения в контрольном справочнике городских адресов, предоставляемом вашей магистралью SIP или поставщиком служб E9-1-1 ТСОП.</span><span class="sxs-lookup"><span data-stu-id="7e75e-105">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="7e75e-106">Подробные сведения о поставщиках услуг SIP E9 – 1 – 1 можно найти [в статье Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7e75e-106">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="7e75e-107">Для получения дополнительных сведений об проверке адресов обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="7e75e-107">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="7e75e-108">**Get — Кслиссервицепровидер**</span><span class="sxs-lookup"><span data-stu-id="7e75e-108">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="7e75e-109">**Set — Кслиссервицепровидер**</span><span class="sxs-lookup"><span data-stu-id="7e75e-109">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="7e75e-110">**Remove — Кслиссервицепровидер**</span><span class="sxs-lookup"><span data-stu-id="7e75e-110">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="7e75e-111">**Get — КслисЦивикаддресс**</span><span class="sxs-lookup"><span data-stu-id="7e75e-111">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="7e75e-112">**Test-КслисЦивикаддресс**</span><span class="sxs-lookup"><span data-stu-id="7e75e-112">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="7e75e-113">Проверка адресов, хранящихся в базе данных местонахождения</span><span class="sxs-lookup"><span data-stu-id="7e75e-113">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="7e75e-114">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7e75e-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7e75e-115">Чтобы настроить подключение к поставщику экстренной службы, выполните следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="7e75e-115">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="7e75e-116">Чтобы проверить адреса, хранящиеся в базе данных местонахождения, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="7e75e-116">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="7e75e-117">Кроме того, для проверки отдельных адресов вы можете использовать командлет **Test-CsLisCivicAddress**.</span><span class="sxs-lookup"><span data-stu-id="7e75e-117">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

