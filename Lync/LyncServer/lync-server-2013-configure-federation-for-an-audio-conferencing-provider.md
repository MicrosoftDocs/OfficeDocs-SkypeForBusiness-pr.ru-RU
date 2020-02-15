---
title: 'Lync Server 2013: Настройка Федерации для поставщика аудио-конференций'
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
ms.openlocfilehash: 4725e80a00da46b7d446b8b8c938b65c569ef8d1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="39398-102">Настройка Федерации для поставщика голосовой конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39398-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39398-103">_**Последнее изменение темы:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="39398-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="39398-104">Если вы хотите использовать поставщика аудио-конференций (ACP) в гибридном развертывании (Lync Server в локальной среде с Lync Online), необходимо настроить федерацию между локальным развертыванием Lync и партнером ACP в качестве разрешенного сервера-партнера.</span><span class="sxs-lookup"><span data-stu-id="39398-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="39398-105">Вы можете настроить федерацию, добавив домен партнера ACP и пограничный сервер (этот способ также может называться прокси-сервером доступа) в список федеративных доменов для локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="39398-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="39398-106">Затем партнеру ACP потребуется добавить полное доменное имя локального пула пограничных серверов в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="39398-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="39398-107">Обратитесь к поставщику ACP для получения дополнительного партнера Детаилсйоур ACP, а затем необходимо добавить полное доменное имя локального пула пограничных серверов в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="39398-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="39398-108">**Добавление домена ACP и пограничного сервера в качестве разрешенного федеративного домена**</span><span class="sxs-lookup"><span data-stu-id="39398-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="39398-109">Чтобы добавить домен ACP в качестве разрешенного сервера-партнера (разрешенный федеративный домен), выполните действия, описанные в разделе [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="39398-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="39398-110">В качестве пограничного сервера Добавьте полное доменное имя пограничного сервера партнера ACP.</span><span class="sxs-lookup"><span data-stu-id="39398-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="39398-111">Вам может потребоваться связаться с партнером ACP, чтобы получить полное доменное имя для пограничного сервера, которое также может называться в качестве прокси-сервера для доступа к вашему почтовому серверу.</span><span class="sxs-lookup"><span data-stu-id="39398-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="39398-112">**Предоставление полного доменного имени пула пограничного сервера партнеру ACP**</span><span class="sxs-lookup"><span data-stu-id="39398-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="39398-113">Партнеру ACP необходимо настроить федерацию, чтобы добавить локальный домен в качестве разрешенного сервера-партнера, добавив полное доменное имя пула пограничного сервера в качестве разрешенного федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="39398-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

