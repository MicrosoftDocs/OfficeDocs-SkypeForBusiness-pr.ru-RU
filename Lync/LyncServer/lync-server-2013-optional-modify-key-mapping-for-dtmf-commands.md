---
title: 'Lync Server 2013: изменение сопоставления клавиш для команд DTMF (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86986ba2715021e7bf39f5d448f9de5f9a733f54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="6a02e-102">Необязательно Изменение сопоставления клавиш для команд DTMF в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a02e-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a02e-103">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6a02e-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6a02e-p101">Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона. Изменить назначения клавиш, используемых для команд DTMF, можно с помощью командлетов. Это действие необязательно.</span><span class="sxs-lookup"><span data-stu-id="6a02e-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. You can use cmdlets to modify the keys used for the DTMF commands. This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a02e-108">Для получения дополнительных сведений об этих командлетах и возможных параметрах DTMF ознакомьтесь с документацией по среде управления Lync Server или командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6a02e-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="6a02e-109">Изменение сопоставления команд DTMF</span><span class="sxs-lookup"><span data-stu-id="6a02e-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="6a02e-110">Войдите на компьютер как член группы **RTCUniversalServerAdmins** или роли **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="6a02e-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="6a02e-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6a02e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6a02e-112">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="6a02e-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="6a02e-113">Этот командлет возвращает параметры DTMF, используемые для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6a02e-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="6a02e-114">Выполните следующий командлет и укажите клавишу, назначаемую каждому параметру, который требуется изменить:</span><span class="sxs-lookup"><span data-stu-id="6a02e-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="6a02e-115">Этот командлет изменяет параметры DTMF, используемые для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6a02e-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="6a02e-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="6a02e-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="6a02e-p102">В этом примере функции клавиш включения и отключения объявлений, а также включения и отключения звука всех участников меняются местами. Поскольку не указано значение параметра Identity, эти изменения применяются к глобальным параметрам DTMF.</span><span class="sxs-lookup"><span data-stu-id="6a02e-p102">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="6a02e-119">Необязательно Чтобы создать дополнительные наборы команд DTMF для определенных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration** с идентификатором сайта.</span><span class="sxs-lookup"><span data-stu-id="6a02e-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="6a02e-120">При создании новых параметров DTMF для сайтов параметры сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="6a02e-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="6a02e-121">Дополнительные сведения см. в документации по среде управления Lync Server или командной консоли командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a02e-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

