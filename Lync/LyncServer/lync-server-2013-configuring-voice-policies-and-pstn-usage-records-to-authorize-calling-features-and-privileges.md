---
title: 'Lync Server 2013: Настройка политик голосовой связи и записей использования PSTN для авторизации функций звонков и привилегий'
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
ms.openlocfilehash: 339eba57121b475732794b15c2c5d16dced303ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="5549c-102">Настройка политики голосовой связи и записей использования PSTN для авторизации функций звонков и привилегий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5549c-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5549c-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="5549c-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="5549c-104">*Политика голосовой связи* определяет набор функций звонков и разрешений, предоставляемых пользователям, которым назначена данная политика, путем связывания с одной или несколькими записями ТСОП.</span><span class="sxs-lookup"><span data-stu-id="5549c-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="5549c-p101">Областью действия политики голосовой связи может быть *сайт* (определяет функции и разрешения по умолчанию для сайта сети) или *пользователь* (определяет функции и разрешения, назначаемые на уровне пользователей или групп). Пользователям, которым не назначена политика голосовой связи, автоматически назначается глобальная политика. Она представляет собой политику голосовой связи по умолчанию, устанавливаемую вместе с продуктом.</span><span class="sxs-lookup"><span data-stu-id="5549c-p101">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis). Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5549c-107">Подробнее о <A href="lync-server-2013-voice-policies.md">политиках голосовой связи в Lync Server 2013</A> можно найти в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="5549c-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5549c-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="5549c-108">In This Section</span></span>

  - [<span data-ttu-id="5549c-109">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5549c-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="5549c-110">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5549c-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="5549c-111">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5549c-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

