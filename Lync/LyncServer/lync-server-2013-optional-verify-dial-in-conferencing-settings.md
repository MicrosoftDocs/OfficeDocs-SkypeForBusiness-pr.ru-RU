---
title: 'Lync Server 2013: Проверка параметров конференц-связи с телефонным подключением (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86ec4e4852594e7e4748213de994b6b4f471d460
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="f3a46-102">Необязательно Проверка параметров конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3a46-102">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3a46-103">_**Последнее изменение темы:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="f3a46-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="f3a46-p101">Чтобы завершить проверку конфигурации конференц-связи с телефонным подключением, выполните поиск абонентских групп с регионом, для которого не задан ни один номер доступа, а также номеров доступа, для которых не задан ни один регион конференц-связи с телефонным подключением. Это шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f3a46-p101">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region. This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="f3a46-106">Поиск абонентских групп с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа</span><span class="sxs-lookup"><span data-stu-id="f3a46-106">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="f3a46-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f3a46-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f3a46-108">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f3a46-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f3a46-109">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f3a46-109">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="f3a46-110">Этот командлет возвращает все абонентские группы с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа.</span><span class="sxs-lookup"><span data-stu-id="f3a46-110">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="f3a46-111">Поиск номеров доступа, которые не связаны ни с одним регионом</span><span class="sxs-lookup"><span data-stu-id="f3a46-111">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="f3a46-112">Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f3a46-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f3a46-113">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f3a46-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f3a46-114">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="f3a46-114">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="f3a46-115">Этот командлет возвращает все номера доступа к конференц-связи с телефонным подключением, которые не связаны ни с одним регионом.</span><span class="sxs-lookup"><span data-stu-id="f3a46-115">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

