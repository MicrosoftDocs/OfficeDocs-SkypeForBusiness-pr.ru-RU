---
title: 'Lync Server 2013: Настройка Федерации для поставщика аудио-конференций'
description: 'Lync Server 2013: Настройка Федерации для поставщика голосовой конференц-связи.'
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
ms.openlocfilehash: c74654224c42618768d881a95031d58be4d55df5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553325"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="19cb4-103">Настройка Федерации для поставщика голосовой конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19cb4-103">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19cb4-104">_**Последнее изменение темы:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="19cb4-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="19cb4-105">Если вы хотите использовать поставщика аудио-конференций (ACP) в гибридном развертывании (Lync Server в локальной среде с Lync Online), необходимо настроить федерацию между локальным развертыванием Lync и партнером ACP в качестве разрешенного сервера-партнера.</span><span class="sxs-lookup"><span data-stu-id="19cb4-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="19cb4-106">Вы можете настроить федерацию, добавив домен партнера ACP и пограничный сервер (этот способ также может называться прокси-сервером доступа) в список федеративных доменов для локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="19cb4-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="19cb4-107">Затем партнеру ACP потребуется добавить полное доменное имя локального пула пограничных серверов в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="19cb4-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="19cb4-108">Обратитесь к поставщику ACP для получения дополнительного партнера Детаилсйоур ACP, а затем необходимо добавить полное доменное имя локального пула пограничных серверов в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="19cb4-108">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="19cb4-109">**Добавление домена ACP и пограничного сервера в качестве разрешенного федеративного домена**</span><span class="sxs-lookup"><span data-stu-id="19cb4-109">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="19cb4-110">Чтобы добавить домен ACP в качестве разрешенного сервера-партнера (разрешенный федеративный домен), выполните действия, описанные в разделе [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="19cb4-110">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="19cb4-111">В качестве пограничного сервера Добавьте полное доменное имя пограничного сервера партнера ACP.</span><span class="sxs-lookup"><span data-stu-id="19cb4-111">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="19cb4-112">Вам может потребоваться связаться с партнером ACP, чтобы получить полное доменное имя для пограничного сервера, которое также может называться в качестве прокси-сервера для доступа к вашему почтовому серверу.</span><span class="sxs-lookup"><span data-stu-id="19cb4-112">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="19cb4-113">**Предоставление полного доменного имени пула пограничного сервера партнеру ACP**</span><span class="sxs-lookup"><span data-stu-id="19cb4-113">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="19cb4-114">Партнеру ACP необходимо настроить федерацию, чтобы добавить локальный домен в качестве разрешенного сервера-партнера, добавив полное доменное имя пула пограничного сервера в качестве разрешенного федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="19cb4-114">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

