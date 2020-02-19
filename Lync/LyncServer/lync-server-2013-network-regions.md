---
title: 'Lync Server 2013: области сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a93e4bda396cb684ee15e5ee8dcd2c90ae09542
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="d8b71-102">Регионы сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8b71-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8b71-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d8b71-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d8b71-104">*Области сети* представляют собой сетевые концентраторы или магистрали, используемые в конфигурации контроля допуска звонков, E9-1-1 и обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d8b71-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="d8b71-105">Следующие процедуры используются для просмотра, создания или изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="d8b71-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="d8b71-106">Например, если области сети уже созданы для одного из компонентов голосовой связи, новые области сети создавать не требуется; остальные расширенные компоненты корпоративной голосовой связи используют те же области сети.</span><span class="sxs-lookup"><span data-stu-id="d8b71-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="d8b71-107">Тем не менее, возможно, потребуется изменить существующее определение области сети, чтобы применить специальные настройки для конкретных компонентов.</span><span class="sxs-lookup"><span data-stu-id="d8b71-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="d8b71-108">Например, когда после создания областей сети для системы E9-1-1 (которой не требуется связанный центральный сайт) выполняется развертывание системы контроля допуска звонков, потребуется изменить определения области сети для указания центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="d8b71-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="d8b71-109">Дополнительные сведения см. [в статье configure Network regions for CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="d8b71-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8b71-110">Все специальные требования в отношении определений области сети для конкретных компонентов указаны в документации по развертыванию данных компонентов.</span><span class="sxs-lookup"><span data-stu-id="d8b71-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8b71-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="d8b71-111">In This Section</span></span>

  - [<span data-ttu-id="d8b71-112">Просмотр сведений о области сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8b71-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="d8b71-113">Создание или изменение областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8b71-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="d8b71-114">Удаление существующих областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8b71-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="d8b71-115">Справка</span><span class="sxs-lookup"><span data-stu-id="d8b71-115">Reference</span></span>

[<span data-ttu-id="d8b71-116">Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8b71-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

