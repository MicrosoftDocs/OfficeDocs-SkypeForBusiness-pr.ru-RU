---
title: 'Lync Server 2013: Удаление диапазона номеров для отправки группового звонка'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b95df76c812b50ff9c220ea208406a5ab7cf2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="5287e-102">Удаление диапазона номеров для отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5287e-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5287e-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5287e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5287e-104">Чтобы удалить диапазон номеров для отправки группового звонка, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5287e-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="5287e-105">Удаление диапазона номеров группы для отправки звонков</span><span class="sxs-lookup"><span data-stu-id="5287e-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="5287e-106">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5287e-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5287e-107">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5287e-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5287e-108">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5287e-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="5287e-109">Например:</span><span class="sxs-lookup"><span data-stu-id="5287e-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5287e-110">Подробнее о дополнительных параметрах можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-кскаллпаркорбит</A>.</span><span class="sxs-lookup"><span data-stu-id="5287e-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5287e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5287e-111">See Also</span></span>


[<span data-ttu-id="5287e-112">Создание или изменение диапазона орбиты на расстоянии вверх на сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5287e-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="5287e-113">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="5287e-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="5287e-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="5287e-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

