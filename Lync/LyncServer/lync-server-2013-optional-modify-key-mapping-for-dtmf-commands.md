---
title: 'Lync Server 2013: изменение назначенных клавиш для команд DTMF (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a9fbe17a07403fbf0195026d44b490680973e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="539ec-102">Изменение назначенных клавиш для команд DTMF в Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="539ec-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="539ec-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="539ec-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="539ec-104">Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF.</span><span class="sxs-lookup"><span data-stu-id="539ec-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="539ec-105">Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона.</span><span class="sxs-lookup"><span data-stu-id="539ec-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="539ec-106">Вы можете использовать командлеты для изменения ключей, используемых для команд DTMF.</span><span class="sxs-lookup"><span data-stu-id="539ec-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="539ec-107">Этот шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="539ec-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="539ec-108">Подробнее об этих командлетах и возможных параметрах DTMF можно найти в разделе Документация оболочки управления Lync Server или командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="539ec-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="539ec-109">Изменение сопоставления клавиш для команд DTMF</span><span class="sxs-lookup"><span data-stu-id="539ec-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="539ec-110">Войдите в систему под учетной записью члена группы **рткуниверсалсерверадминс** или члена роли **CS-серверадминистратор** или **ксадминистратор** .</span><span class="sxs-lookup"><span data-stu-id="539ec-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="539ec-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="539ec-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="539ec-112">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="539ec-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="539ec-113">Этот командлет возвращает параметры DTMF, используемые для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="539ec-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="539ec-114">Выполните следующий командлет и укажите клавишу, которую нужно нажимать для каждого параметра, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="539ec-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="539ec-115">Этот командлет изменяет параметры DTMF, используемые для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="539ec-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="539ec-116">Например:</span><span class="sxs-lookup"><span data-stu-id="539ec-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="539ec-117">В этом примере заменяется клавиша, нажатная для включения или отключения объявлений, и нажатие клавиши, позволяющей отключить Микрофоны всех участников.</span><span class="sxs-lookup"><span data-stu-id="539ec-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="539ec-118">Поскольку удостоверение не задано, эти изменения применяются к глобальным параметрам DTMF.</span><span class="sxs-lookup"><span data-stu-id="539ec-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="539ec-119">(Дополнительно). Чтобы создать дополнительные наборы команд DTMF для конкретных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration**, указав идентификатор сайта.</span><span class="sxs-lookup"><span data-stu-id="539ec-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="539ec-120">При создании новых параметров DTMF для сайтов эти параметры сайтов имеют приоритет перед глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="539ec-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="539ec-121">Дополнительные сведения можно найти в разделе Документация оболочки управления Lync Server или командной строки оболочки Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="539ec-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

