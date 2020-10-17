---
title: Предложен Создание каталогов конференций
description: Предложен Создание каталогов конференций.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b14982893fbc14a87818875a787d0f776da84ae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563665"
---
# <a name="recommended-create-conference-directories"></a><span data-ttu-id="eb801-103">Предложен Создание каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="eb801-103">(Recommended) Create Conference Directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb801-104">_**Последнее изменение темы:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="eb801-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="eb801-105">Каталоги конференций поддерживают сопоставление буквенно-цифрового идентификатора собраний, который участник использует для присоединения к Конференции при использовании Lync 2013, и идентификатор одноранговой конференции, который используется участником конференц-связи с телефонным подключением для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="eb801-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="eb801-106">Формат идентификатора конференции:</span><span class="sxs-lookup"><span data-stu-id="eb801-106">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="eb801-107">Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций.</span><span class="sxs-lookup"><span data-stu-id="eb801-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="eb801-108">В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="eb801-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="eb801-109">Это правило позволит сохранить короткие идентификаторы конференций.</span><span class="sxs-lookup"><span data-stu-id="eb801-109">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="eb801-110">Тем не менее, если число каталогов конференций (в пулах) превышает 9, длина идентификатора конференции увеличится для поддержки дополнительных конференций.</span><span class="sxs-lookup"><span data-stu-id="eb801-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="eb801-111">Создание каталога конференций</span><span class="sxs-lookup"><span data-stu-id="eb801-111">Creating a conference directory</span></span>

1.  <span data-ttu-id="eb801-112">В командной консоли Lync Server введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="eb801-112">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="eb801-113">Например, в следующем примере создается каталог конференций с идентификатором 42, размещенном в пуле atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="eb801-113">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb801-114">См. также</span><span class="sxs-lookup"><span data-stu-id="eb801-114">See Also</span></span>


[<span data-ttu-id="eb801-115">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb801-115">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="eb801-116">New — CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="eb801-116">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

