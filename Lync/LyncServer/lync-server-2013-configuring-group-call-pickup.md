---
title: 'Lync Server 2013: Настройка отправки группового звонка'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3096c468b478da365bcfa0e38fa287a5c2ab57a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="37753-102">Настройка отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37753-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37753-103">_**Тема последнего изменения:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="37753-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="37753-104">Накопительное обновление для Lync Server 2013: Февраль 2013 вводит функцию отправки группового звонка в качестве новой функции голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37753-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="37753-105">Отправка группового звонка позволяет пользователям совершать звонки, которые поступают за другие пользователи, набрав номер группы для отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="37753-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="37753-106">Компоненты, используемые для отправки группового звонка, автоматически устанавливаются и включаются на сервере переднего плана или стандартном сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37753-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="37753-107">Однако необходимо настроить раскладки групповых звонков, прежде чем она будет доступна для пользователей.</span><span class="sxs-lookup"><span data-stu-id="37753-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="37753-108">Этот раздел поможет вам пройти настройку отправки группового звонка.</span><span class="sxs-lookup"><span data-stu-id="37753-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37753-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="37753-109">In This Section</span></span>

[<span data-ttu-id="37753-110">Необходимые условия для настройки раскладки группового звонка и права пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37753-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="37753-111">Процесс развертывания для отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37753-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="37753-112">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37753-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="37753-113">Настройка номеров групп для отправки звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37753-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="37753-114">Включение отправки группового звонка для пользователей в Lync Server 2013 и назначение номера группы</span><span class="sxs-lookup"><span data-stu-id="37753-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="37753-115">Связь групп раскладки звонков для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37753-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="37753-116">Необязательно Проверка развертывания отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37753-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

