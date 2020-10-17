---
title: 'Lync Server 2013: запуск служб на серверах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532966"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="45de1-102">Запуск служб на серверах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45de1-102">Start services on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45de1-103">_**Последнее изменение темы:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="45de1-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="45de1-104">Для успешного выполнения этой процедуры необходимо войти в систему с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="45de1-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="45de1-105">Дополнительные сведения о делегировании разрешений представлены в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="45de1-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="45de1-106">После установки локального хранилища конфигурации на серверах установите компоненты Lync Server 2013 и настройте сертификаты на сервере переднего плана или сервере переднего плана, необходимо запустить службы Lync Server 2013 на сервере.</span><span class="sxs-lookup"><span data-stu-id="45de1-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="45de1-107">Используйте следующую процедуру для запуска служб на каждом сервере переднего плана в развертывании.</span><span class="sxs-lookup"><span data-stu-id="45de1-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="45de1-108">Запуск служб на сервере переднего плана или в стандартном выпуске сервера</span><span class="sxs-lookup"><span data-stu-id="45de1-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="45de1-109">В мастере развертывания Lync Server на странице **Lync server 2013** нажмите **выполнить** рядом с **шагом 4: Start Services**.</span><span class="sxs-lookup"><span data-stu-id="45de1-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="45de1-110">На странице **Запуск служб** нажмите кнопку **Далее** , чтобы запустить службы Lync Server на сервере.</span><span class="sxs-lookup"><span data-stu-id="45de1-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="45de1-111">После того как все службы будут успешно запущены, на странице **Выполнение команд** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="45de1-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45de1-112">Использование команды для запуска служб на сервере — это лучший способ, позволяющий получить подтверждение того, что службы действительно запущены.</span><span class="sxs-lookup"><span data-stu-id="45de1-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="45de1-113">Однако он может не отражать фактическое состояние служб.</span><span class="sxs-lookup"><span data-stu-id="45de1-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="45de1-114">Рекомендуется использовать шаг <STRONG>Service Status (Optional)</STRONG> (Состояние службы (дополнительно)) сразу после шага <STRONG>Запуск служб</STRONG>, чтобы открыть консоль управления (MMC) и убедиться в том, что все службы успешно запущены.</span><span class="sxs-lookup"><span data-stu-id="45de1-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="45de1-115">Если какая – либо служба Lync Server не запущена, можно щелкнуть ее правой кнопкой мыши в консоли MMC и выбрать команду <STRONG>Пуск</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="45de1-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

