---
title: 'Lync Server 2013: необходимое программное обеспечение для корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb85a8da9fe0d009f46ef23b919aeb9fd006fab4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="15c77-102">Необходимое программное обеспечение для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15c77-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15c77-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="15c77-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="15c77-104">Убедитесь в том, что инфраструктура, в которой вы планируете развернуть корпоративный голос, соответствует следующим требованиям к программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="15c77-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="15c77-105">Lync Server 2013 Standard Edition или Enterprise Edition установлен и работает в сети.</span><span class="sxs-lookup"><span data-stu-id="15c77-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="15c77-106">Все пограничные серверы развертываются и работают в демилитаризованной зоне, в том числе на пограничные серверы, на которых работает служба EDGE, служба EDGE, служба Edge для веб-конференций и обратный прокси.</span><span class="sxs-lookup"><span data-stu-id="15c77-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="15c77-107">Microsoft Exchange Server 2007 с пакетом обновления 3 (SP3), Microsoft Exchange Server 2010 или Microsoft Exchange Server 2013 требуется для интеграции единой системы обмена сообщениями Exchange с сервером Lync, а также для предоставления подробных уведомлений и ведения журнала звонков Конечные точки Lync.</span><span class="sxs-lookup"><span data-stu-id="15c77-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="15c77-108">У вас есть один или несколько пользователей, которые были созданы и включены для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15c77-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="15c77-109">Клиенты и устройства Lync успешно развернуты.</span><span class="sxs-lookup"><span data-stu-id="15c77-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="15c77-110">Построитель топологии установлен на сервере в сети.</span><span class="sxs-lookup"><span data-stu-id="15c77-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="15c77-111">Дальнейшие действия: Проверка требований к безопасности и конфигурации</span><span class="sxs-lookup"><span data-stu-id="15c77-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="15c77-112">После проверки требований к программному обеспечению для корпоративной голосовой связи вы можете использовать документацию для продолжения подготовки к развертыванию корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="15c77-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="15c77-113">Проверьте безопасность, конфигурацию пользователя и оборудование перкуиситес, как описано в разделе [требования к безопасности и конфигурации для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="15c77-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="15c77-114">Установите сервер-посредник, как описано в разделе [Установка сервера исправлений в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), но *только* в том случае, если вы хотите развернуть сервер изолированных обновлений или пул, так как серверы-исправления устанавливаются в рамках пула переднего плана или процесса развертывания сервера Standard Edition при размещении.</span><span class="sxs-lookup"><span data-stu-id="15c77-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="15c77-115">Настройте магистральные подключения для предоставления доступа к PSTN для пользователей, как описано в разделе [Настройка каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="15c77-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

