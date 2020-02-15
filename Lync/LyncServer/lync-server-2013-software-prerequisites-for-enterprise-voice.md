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
ms.openlocfilehash: dc6c5e5f3f9fc92f56ee1f044419f67f5ded32ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a6efa-102">Необходимое программное обеспечение для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6efa-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6efa-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a6efa-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a6efa-104">Убедитесь в том, что инфраструктура, в которой вы планируете развертывать корпоративную голосовую связь, соответствует следующим предварительным требованиям к программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="a6efa-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="a6efa-105">Lync Server 2013 Standard Edition или Enterprise Edition установлен и работает в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="a6efa-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="a6efa-106">Все пограничные серверы развернуты и работают в сети периметра, включая пограничные серверы, на которых работает пограничная служба доступа, пограничная служба аудио-и видеоконференций, пограничная служба веб-конференций и обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="a6efa-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="a6efa-107">Microsoft Exchange Server 2007 с пакетом обновления 3 (SP3), Microsoft Exchange Server 2010 или Microsoft Exchange Server 2013 требуется для интеграции единой системы обмена сообщениями Exchange с Lync Server, а также для предоставления расширенных уведомлений и сведений о журналах вызовов для Конечные точки Lync.</span><span class="sxs-lookup"><span data-stu-id="a6efa-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="a6efa-108">Один или несколько пользователей были созданы и включены для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6efa-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="a6efa-109">Клиенты и устройства Lync успешно развернуты.</span><span class="sxs-lookup"><span data-stu-id="a6efa-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="a6efa-110">Построитель топологий установлен на сервере в сети.</span><span class="sxs-lookup"><span data-stu-id="a6efa-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="a6efa-111">Дальнейшие действия: проверка выполнения требований к безопасности и конфигурации</span><span class="sxs-lookup"><span data-stu-id="a6efa-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="a6efa-112">Проверив выполнение требований к программному обеспечению, вы можете продолжить подготовку к развертыванию корпоративной голосовой связи с помощью этой документации.</span><span class="sxs-lookup"><span data-stu-id="a6efa-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="a6efa-113">Проверьте безопасность, конфигурацию пользователя и оборудование перкуиситес, как описано в статье [требования к безопасности и конфигурации для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="a6efa-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="a6efa-114">Установите сервер-посредник, как описано в [статье Установка файлов для сервера-посредника в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), но *только* в том случае, если требуется развернуть автономный сервер-посредник или пул, так как серверы-посредники устанавливаются как часть пула переднего плана или процесса развертывания сервера Standard Edition при совместном размещении.</span><span class="sxs-lookup"><span data-stu-id="a6efa-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="a6efa-115">Настройте магистральные подключения для предоставления доступа к PSTN для пользователей, как описано в разделе [Настройка магистральных каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="a6efa-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

