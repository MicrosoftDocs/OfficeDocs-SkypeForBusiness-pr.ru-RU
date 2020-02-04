---
title: 'Lync Server 2013: регионы сети'
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
ms.openlocfilehash: 4085b3c554429c960e6f9f558f82366d7b2b2532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="d8afa-102">Регионы сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8afa-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8afa-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d8afa-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d8afa-104">*Регионы сетей* — это сетевые разветвители и одинарные кости, используемые в настройке управления допуском звонков, E9-1-1 и мультимедийными пропусками.</span><span class="sxs-lookup"><span data-stu-id="d8afa-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="d8afa-105">Следующие процедуры служат для просмотра, создания и изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="d8afa-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="d8afa-106">Например, если вы уже создали сетевые регионы для одной голосовой связи, вам не нужно создавать новые сетевые регионы; другие дополнительные функции для корпоративной голосовой связи будут использовать те же сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="d8afa-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="d8afa-107">Однако вам может потребоваться изменить существующее определение области сети для применения параметров, относящихся к функции.</span><span class="sxs-lookup"><span data-stu-id="d8afa-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="d8afa-108">Например, если вы создали области сети для службы E9-1-1, для которой не требуется связанный центральный сайт, и затем развернули службу контроля допуска звонков, вам потребуется изменить определения областей сети, чтобы указать центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="d8afa-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="d8afa-109">Подробности можно найти [в разделе Настройка регионов сети для CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="d8afa-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8afa-110">Любые особые требования к функциональным возможностям для определений сетевых областей описаны в разделе Развертывание для этой функции.</span><span class="sxs-lookup"><span data-stu-id="d8afa-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8afa-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="d8afa-111">In This Section</span></span>

  - [<span data-ttu-id="d8afa-112">Просмотр сведений о сетевом регионе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8afa-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="d8afa-113">Создание и изменение областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8afa-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="d8afa-114">Удаление существующих областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8afa-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="d8afa-115">Справка</span><span class="sxs-lookup"><span data-stu-id="d8afa-115">Reference</span></span>

[<span data-ttu-id="d8afa-116">Развертывание улучшенных функций голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8afa-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

