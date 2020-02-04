---
title: 'Lync Server 2013: настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9f7da3f8560ae0a897211405d686d9ed35101e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="14f41-102">Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14f41-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14f41-103">_**Тема последнего изменения:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="14f41-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="14f41-104">*Политика голосовой связи* включает набор функций звонка и связывает одну или несколько записей использования PSTN для определения функций звонков и разрешений пользователей, которым назначена политика.</span><span class="sxs-lookup"><span data-stu-id="14f41-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="14f41-105">Область политики голосовой связи может быть либо *сайтом* (которая определяет возможности и разрешения по умолчанию для сайта сети), либо *пользователем* (который определяет возможности и разрешения, назначаемые для отдельных пользователей или групп).</span><span class="sxs-lookup"><span data-stu-id="14f41-105">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis).</span></span> <span data-ttu-id="14f41-106">Пользователям, которым не назначена политика голосовой связи, будет автоматически назначаться Глобальная политика, которая является политикой голосовой связи по умолчанию, установленной вместе с продуктом.</span><span class="sxs-lookup"><span data-stu-id="14f41-106">Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14f41-107">Подробные сведения можно найти <A href="lync-server-2013-voice-policies.md">в разделе политики голосовой связи в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="14f41-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="14f41-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="14f41-108">In This Section</span></span>

  - [<span data-ttu-id="14f41-109">Создание политики голосовой связи и настройка записей об использовании PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14f41-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="14f41-110">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14f41-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="14f41-111">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14f41-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

