---
title: 'Lync Server 2013: Настройка Федерации для поставщика голосовой конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="fbd9d-102">Настройка Федерации для поставщика голосовой конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbd9d-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbd9d-103">_**Тема последнего изменения:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="fbd9d-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="fbd9d-104">Если вы хотите использовать поставщика голосовой конференц-связи (ACP) в гибридном развертывании (Lync Server в локальной среде Lync Online), вам нужно настроить федерацию между локальным развертыванием Lync и партнером ACP в качестве разрешенного сервера-партнера.</span><span class="sxs-lookup"><span data-stu-id="fbd9d-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="fbd9d-105">Вы можете настроить федерацию, добавив домен партнера ACP и пограничный сервер (этот способ также может называться прокси-сервером доступа) в список федеративных доменов для локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="fbd9d-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="fbd9d-106">Для вашего партнера ACP необходимо добавить полное доменное имя пула из локального пограничного сервера в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="fbd9d-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="fbd9d-107">Обратитесь к поставщику ACP за дополнительным партнером Детаилсйоур, а затем добавьте полное доменное имя пула из вашего домена пограничного сервера в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="fbd9d-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="fbd9d-108">**Добавление домена ACP и пограничного сервера в качестве разрешенных федеративных доменов**</span><span class="sxs-lookup"><span data-stu-id="fbd9d-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="fbd9d-109">Чтобы добавить домен ACP в качестве разрешенного сервера-партнера (разрешенного федеративного домена), выполните действия, описанные в разделе [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="fbd9d-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="fbd9d-110">Для пограничного сервера добавьте полное доменное имя пограничного сервера партнера ACP.</span><span class="sxs-lookup"><span data-stu-id="fbd9d-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="fbd9d-111">Может потребоваться связаться со своим партнером ACP, чтобы получить полное доменное имя для своего пограничного сервера, на который ваши ACP могут ссылаться как на свой прокси-сервер доступа.</span><span class="sxs-lookup"><span data-stu-id="fbd9d-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="fbd9d-112">**Предоставление полного доменного имени пула пограничного сервера партнеру ACP**</span><span class="sxs-lookup"><span data-stu-id="fbd9d-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="fbd9d-113">Партнеру ACP необходимо настроить федерацию, чтобы добавить ваш локальный домен как разрешенный сервер-партнер, добавив полное доменное имя пула пограничных серверов в качестве разрешенного федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="fbd9d-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

