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
ms.openlocfilehash: ac6dce30e356ed3161f985f32d8f26dc0e34ac6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="51b0f-102">Развертывание клиентов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51b0f-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51b0f-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="51b0f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="51b0f-104">После миграции пользователей на Lync Server 2013 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="51b0f-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="51b0f-105">Используйте фильтр версий клиентов на новом сервере Lync Server 2013, чтобы разрешить вход только клиентам с последними установленными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="51b0f-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="51b0f-106">При необходимости настройте параметры групповой политики, необходимые для начальной загрузки клиентов.</span><span class="sxs-lookup"><span data-stu-id="51b0f-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="51b0f-107">Дополнительные сведения приведены в статье [Настройка политик начальной загрузки клиентов в Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="51b0f-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="51b0f-108">Конфигурация этих параметров необходима только в том случае, если необходимо изменить существующие политики начальной загрузки клиентов или если необходимо задать новые политики начальной загрузки клиентов.</span><span class="sxs-lookup"><span data-stu-id="51b0f-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="51b0f-109">Если не планируется менять политики начальной загрузки клиентов или необходимо сохранить действие устаревших политик начальной загрузки клиентов, нет необходимости предпринимать каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="51b0f-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="51b0f-110">Настройте другие политики пользователей и клиентов для определенных пользователей или групп пользователей с помощью панели управления Lync Server 2013, командной консоли Lync Server 2013 или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="51b0f-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="51b0f-111">Дополнительные сведения приведены в статье [Создание и изменение параметров для Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="51b0f-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="51b0f-112">Разверните последнюю версию Lync Server 2013 Clients и последние накопительные пакеты обновления.</span><span class="sxs-lookup"><span data-stu-id="51b0f-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="51b0f-113">Сведения о развертывании [клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) содержатся в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="51b0f-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="51b0f-114">Необязательно Если в Организации требуется расширенный режим конфиденциальности Lync Server 2013, то после завершения миграции Определите правило политики версий клиентов, чтобы не допустить входа более ранних версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="51b0f-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="51b0f-115">Затем включите расширенный режим конфиденциальности присутствия.</span><span class="sxs-lookup"><span data-stu-id="51b0f-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="51b0f-116">Не включайте режим конфиденциальности расширенного присутствия в Lync 2013 до тех пор, пока у каждого пользователя в данном пуле серверов не будут установлены текущие версии клиентов.</span><span class="sxs-lookup"><span data-stu-id="51b0f-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

