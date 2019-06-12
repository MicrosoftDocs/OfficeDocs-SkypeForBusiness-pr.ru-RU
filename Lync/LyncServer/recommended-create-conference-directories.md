---
title: Создание каталогов конференций (обязательно)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e912beac1eeffe3214f8a8d638926d84f547a270
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="27d4f-102">Создание каталогов конференций (обязательно)</span><span class="sxs-lookup"><span data-stu-id="27d4f-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27d4f-103">_**Тема последнего изменения:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="27d4f-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="27d4f-104">В каталогах конференций поддерживается сопоставление буквенно-цифровых ИДЕНТИФИКАТОРов собраний, используемых участниками для присоединения к Конференции с помощью Lync 2013, а также идентификатора конференции, который используется участниками конференц-связи с телефонным подключением для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="27d4f-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="27d4f-105">Идентификатор конференции представлен в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="27d4f-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="27d4f-106">Создание нескольких каталогов конференций позволяет присваивать конференциям короткие идентификаторы, если количество конференций не слишком велико.</span><span class="sxs-lookup"><span data-stu-id="27d4f-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="27d4f-107">В организациях, где количество конференций на каждого пользователя находится в обычных пределах, рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="27d4f-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="27d4f-108">С помощью этого правила идентификаторы конференций обычно можно оставлять небольшим.</span><span class="sxs-lookup"><span data-stu-id="27d4f-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="27d4f-109">Однако когда количество каталогов конференций (по пулам) превышает 9, длина идентификатора конференции будет увеличиваться для поддержки дополнительных конференций.</span><span class="sxs-lookup"><span data-stu-id="27d4f-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="27d4f-110">Создание каталога конференций</span><span class="sxs-lookup"><span data-stu-id="27d4f-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="27d4f-111">В командной консоли Lync Server введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="27d4f-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="27d4f-112">Например, в следующем примере создается каталог конференций с удостоверением 42, размещенным в пуле atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="27d4f-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27d4f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="27d4f-113">See Also</span></span>


[<span data-ttu-id="27d4f-114">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d4f-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="27d4f-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="27d4f-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

