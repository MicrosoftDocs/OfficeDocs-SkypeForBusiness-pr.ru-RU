---
title: Развертывание клиентов Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="6f923-102">Развертывание клиентов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f923-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f923-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6f923-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6f923-104">После миграции пользователей на Lync Server 2013 выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6f923-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="6f923-105">С помощью фильтра Client Version (клиентская версия) на новом сервере Lync Server 2013 разрешите только клиентам с установленными последними обновлениями, чтобы войти в систему.</span><span class="sxs-lookup"><span data-stu-id="6f923-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="6f923-106">При необходимости настройте параметры групповой политики, необходимые для начальной загрузки клиента.</span><span class="sxs-lookup"><span data-stu-id="6f923-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="6f923-107">Подробности можно найти в разделе [Настройка политик начальной настройки клиента в Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6f923-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="6f923-108">Настройка этих параметров требуется только в том случае, если вы хотите изменить существующие политики начальной настройки клиента или настроить новые политики начальной настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="6f923-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="6f923-109">Если вы не планируете настраивать политики начальной настройки клиента или хотите, чтобы политики начальной загрузки устаревшего клиента оставались в силе, никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="6f923-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="6f923-110">Настройте другие политики пользователей и клиентов для определенных пользователей или групп пользователей с помощью панели управления Lync Server 2013, командной консоли Lync Server 2013 или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="6f923-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="6f923-111">Подробные сведения можно найти в разделе [новые и измененные параметры Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="6f923-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="6f923-112">Развертывание последней версии клиентов Lync Server 2013 вместе с последними накопительными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="6f923-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="6f923-113">Подробные сведения можно найти [в разделе Развертывание клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6f923-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="6f923-114">Необязательно Если в вашей организации требуется расширенный режим конфиденциальности Lync Server 2013 после завершения миграции, определите правило политики для версии клиента, чтобы предотвратить вход более ранних версий клиента.</span><span class="sxs-lookup"><span data-stu-id="6f923-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="6f923-115">Затем включите режим расширенной защиты сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="6f923-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6f923-116">Не включайте режим конфиденциальности для расширенного присутствия в Lync 2013, пока у каждого пользователя в данном пуле серверов не будет установлено Последнее количество клиентских версий.</span><span class="sxs-lookup"><span data-stu-id="6f923-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

