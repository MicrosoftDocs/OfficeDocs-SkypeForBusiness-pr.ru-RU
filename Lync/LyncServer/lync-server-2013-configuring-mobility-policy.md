---
title: 'Lync Server 2013: Настройка политики мобильности'
description: 'Lync Server 2013: Настройка политики мобильности.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbbf7f9db54c8436f2db24d593dbd7a1372d5e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570005"
---
# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="74899-103">Настройка политики мобильности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74899-103">Configuring mobility policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74899-104">_**Последнее изменение темы:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="74899-104">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="74899-105">Lync Server 2013 предоставляет политики мобильности, которые определяют, кто может использовать функции мобильности, звонить через Works, Voice over IP (VoIP) или видео, а также требуется ли WiFi для VoIP или видео.</span><span class="sxs-lookup"><span data-stu-id="74899-105">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="74899-106">Функция "позвонить с рабочего" позволяет пользователям мобильных устройств совершать и принимать звонки на мобильный телефон, используя номер рабочего телефона вместо номера мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="74899-106">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="74899-107">Эта функция запрещает вызываемому абоненту Просмотр номера мобильного телефона вызывающего абонента и позволяет пользователю избежать оплаты за исходящие звонки.</span><span class="sxs-lookup"><span data-stu-id="74899-107">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="74899-108">Настройка VoIP и видео дает пользователям возможность принимать и совершать звонки VoIP и видео.</span><span class="sxs-lookup"><span data-stu-id="74899-108">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="74899-109">Параметры использования Wi-Fi определите, будет ли устройство пользователя использовать сеть Wi-Fi через сотовую сеть передачи данных.</span><span class="sxs-lookup"><span data-stu-id="74899-109">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="74899-110">По умолчанию мобильность, Звонок через Work и функции VoIP и видео включены.</span><span class="sxs-lookup"><span data-stu-id="74899-110">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="74899-111">Параметры, требующие использования WiFi для VoIp и видео, отключены.</span><span class="sxs-lookup"><span data-stu-id="74899-111">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="74899-112">Администраторы могут указывать, кому следует предоставить доступ к этим функциям, путем выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="74899-112">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="74899-113">Можно отключить эти функции на глобальном уровне, на уровне узла или пользователя.</span><span class="sxs-lookup"><span data-stu-id="74899-113">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="74899-114">Использование мобильных функций и функции «Позвонить с рабочего» возможно при условии соблюдения следующих предварительных требований:</span><span class="sxs-lookup"><span data-stu-id="74899-114">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="74899-115">Пользователи должны быть включены для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74899-115">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="74899-116">Для пользователей должна быть включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="74899-116">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="74899-117">Пользователям необходимо назначить политику мобильности с установленным значением True для параметра **EnableMobility**.</span><span class="sxs-lookup"><span data-stu-id="74899-117">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="74899-118">Чтобы пользователи могли использовать функцию «Позвонить с рабочего», необходимо соблюдение двух дополнительных предварительных требований:</span><span class="sxs-lookup"><span data-stu-id="74899-118">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="74899-119">Пользователям должна быть назначена политика голосовой связи с выбранной функцией **Разрешить одновременный звонок на несколько телефонов**.</span><span class="sxs-lookup"><span data-stu-id="74899-119">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="74899-120">Пользователям необходимо назначить политику мобильности с установленным значением True для параметра **EnableOutsideVoice**.</span><span class="sxs-lookup"><span data-stu-id="74899-120">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74899-121">Пользователи, не поддерживающие корпоративную голосовую связь, могут использовать свои мобильные устройства для совершения звонков Lync по ПРОТОКОЛу VoIP (VoIP) или присоединяться к конференциям с помощью ссылки щелкните, чтобы присоединиться к их мобильным устройствам, если назначить этим пользователям соответствующие параметры политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="74899-121">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="74899-122">Дополнительную информацию можно узнать <A href="lync-server-2013-defining-your-mobility-requirements.md">в статье Определение требований к мобильности для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="74899-122">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="74899-123">Дополнительные сведения о включении пользователей для Lync Server 2013 приведены в статье [Отключение или повторное включение учетной записи пользователя для Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="74899-123">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="74899-124">Более подробную информацию о включении пользователей для корпоративной голосовой связи можно узнать [в статье Включение поддержки корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="74899-124">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="74899-125">Подробнее о настройке параметров политики голосовой связи можно узнать [в статье изменение политики голосовой связи и настройке записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="74899-125">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="74899-126">Изменение глобальной мобильной политики</span><span class="sxs-lookup"><span data-stu-id="74899-126">To modify global mobility policy</span></span>

1.  <span data-ttu-id="74899-127">Выполните вход на любой компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74899-127">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="74899-128">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74899-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="74899-p105">Отключите доступ к мобильной функции и функции «Позвонить с рабочего» на глобальном уровне. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="74899-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74899-p106">Можно отключить функцию «Позвонить с рабочего» без выключения доступа к функции мобильности. Однако вы не можете отключить функцию без выключения функции «Позвонить с рабочего».</span><span class="sxs-lookup"><span data-stu-id="74899-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="74899-133">Изменение мобильной политики на уровне узла</span><span class="sxs-lookup"><span data-stu-id="74899-133">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="74899-134">Выполните вход на любой компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74899-134">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="74899-135">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74899-135">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="74899-136">Создайте политику на уровне сайта и отключите VoIP и видео, а затем включите параметр требовать WiFi для протокола IP Audio и для IP-видео по сайту.</span><span class="sxs-lookup"><span data-stu-id="74899-136">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="74899-137">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="74899-137">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="74899-138">Изменение мобильной политики на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="74899-138">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="74899-139">Выполните вход на любой компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74899-139">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="74899-140">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74899-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="74899-p108">Создайте мобильные политики на уровне пользователя и выключите функцию мобильности и функцию «Позвонить с рабочего» для конкретных пользователей. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="74899-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="74899-p109">Можно отключить функцию «Позвонить с рабочего» без выключения доступа к функции мобильности. Однако вы не можете отключить функцию без выключения функции «Позвонить с рабочего».</span><span class="sxs-lookup"><span data-stu-id="74899-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="74899-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="74899-145">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74899-146">См. также</span><span class="sxs-lookup"><span data-stu-id="74899-146">See Also</span></span>


[<span data-ttu-id="74899-147">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74899-147">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="74899-148">Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74899-148">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="74899-149">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74899-149">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="74899-150">Определение требований к мобильности для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74899-150">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="74899-151">New — CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="74899-151">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="74899-152">Set — CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="74899-152">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="74899-153">Get — CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="74899-153">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="74899-154">Granting — CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="74899-154">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="74899-155">Remove — CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="74899-155">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

