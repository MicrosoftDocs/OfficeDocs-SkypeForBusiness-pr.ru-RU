---
title: 'Lync Server 2013: Настройка групповой отправки вызовов'
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
ms.openlocfilehash: bb001ef032a89d6225e493366c8df01333180d00
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="de33c-102">Настройка групповой отправки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de33c-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de33c-103">_**Последнее изменение темы:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="de33c-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="de33c-104">Накопительный пакет обновления для Lync Server 2013: в феврале 2013 появился новый компонент корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="de33c-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="de33c-105">Групповое получение звонков позволяет пользователям получать звонки, которые вызывают звонок для другого пользователя с помощью набора номера группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="de33c-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="de33c-106">Компоненты, используемые при групповой отправке звонков, автоматически устанавливаются и включаются на сервере переднего плана или сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="de33c-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="de33c-107">Тем не менее, необходимо настроить отправку групповых вызовов, прежде чем она будет доступна пользователям.</span><span class="sxs-lookup"><span data-stu-id="de33c-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="de33c-108">В этом разделе рассказывается о настройке групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="de33c-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="de33c-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="de33c-109">In This Section</span></span>

[<span data-ttu-id="de33c-110">Требования к настройке группового ответа на звонки и пользовательские права в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de33c-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="de33c-111">Процесс развертывания для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de33c-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="de33c-112">Развертывание средства SEFAUtil в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de33c-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="de33c-113">Настройка номеров групп для ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de33c-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="de33c-114">Включение групповой отправки звонков для пользователей в Lync Server 2013 и назначение номера группы</span><span class="sxs-lookup"><span data-stu-id="de33c-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="de33c-115">Обмен назначениями группового ответа на звонки пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de33c-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="de33c-116">Необязательно Проверка развертывания группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de33c-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

