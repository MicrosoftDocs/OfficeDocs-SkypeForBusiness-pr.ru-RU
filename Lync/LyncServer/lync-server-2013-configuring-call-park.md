---
title: 'Lync Server 2013: Настройка парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d96b75072a2d23773feef0cf5095345ddeb7322
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="68dbe-102">Настройка парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68dbe-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="68dbe-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="68dbe-104">Парковки вызовов позволяет пользователю корпоративной голосовой связи выполнять вызов на удержании с одного телефона и затем извлекать вызов позже, набираемый внутренний номер (как *орбиту*парковки вызовов) с любого телефона.</span><span class="sxs-lookup"><span data-stu-id="68dbe-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="68dbe-105">Компоненты, используемые для парковки вызовов, автоматически устанавливаются и включаются на сервере переднего плана или сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="68dbe-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="68dbe-106">Тем не менее, необходимо настроить парковки вызовов, прежде чем он будет доступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="68dbe-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="68dbe-107">В этом разделе описывается настройка парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="68dbe-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68dbe-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="68dbe-108">In This Section</span></span>

  - [<span data-ttu-id="68dbe-109">Необходимые условия и права пользователя для настройки парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="68dbe-110">Процесс развертывания для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="68dbe-111">Настройка таблицы орбит парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="68dbe-112">Настройка параметров парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="68dbe-113">Настройка музыки парковки вызовов на удержании в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="68dbe-114">Включение парковки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="68dbe-115">Проверка правил нормализации для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="68dbe-116">Необязательно Проверка развертывания парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68dbe-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

