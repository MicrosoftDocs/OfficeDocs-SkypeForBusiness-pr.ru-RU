---
title: 'Lync Server 2013: настройка политики мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="f1712-102">Настройка политики мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1712-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1712-103">_**Тема последнего изменения:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="f1712-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="f1712-104">Lync Server 2013 предоставляет политики для мобильных устройств, которые определяют, кто может использовать возможности мобильных устройств, звонки через Works, Voice по протоколу IP (VoIP) или видео, а также требуется ли WiFi для VoIP или видео.</span><span class="sxs-lookup"><span data-stu-id="f1712-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="f1712-105">Функция "позвонить с помощью рабочих возможностей" позволяет мобильному пользователю совершать и принимать звонки с мобильного телефона с помощью рабочего номера вместо номера мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="f1712-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="f1712-106">Эта функция предотвращает просмотр номера мобильного телефона вызывающего абонента и позволяет пользователю избежать оплаты за исходящие звонки.</span><span class="sxs-lookup"><span data-stu-id="f1712-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="f1712-107">Настройка VoIP и видео дает возможность пользователям принимать и совершать звонки и видео по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="f1712-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="f1712-108">Параметры использования WiFi определяют, требуется ли устройству пользователя возможность использования сети Wi-Fi для мобильной сети передачи данных.</span><span class="sxs-lookup"><span data-stu-id="f1712-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="f1712-109">По умолчанию мобильные устройства, звонки через Work и функции VoIP и видео включены.</span><span class="sxs-lookup"><span data-stu-id="f1712-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="f1712-110">Параметры, необходимые для использования WiFi для VoIp и видео, отключены.</span><span class="sxs-lookup"><span data-stu-id="f1712-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="f1712-111">Администраторы могут определить, кто имеет доступ к этим функциям, выполнив командлет.</span><span class="sxs-lookup"><span data-stu-id="f1712-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="f1712-112">Вы можете отключить параметры глобально, по сайту или по пользователю.</span><span class="sxs-lookup"><span data-stu-id="f1712-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="f1712-113">Для использования функций мобильной связи и звонков через Work пользователи должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="f1712-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="f1712-114">Пользователи должны быть включены для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1712-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="f1712-115">Пользователи должны быть включены для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f1712-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="f1712-116">Пользователям должны быть назначены правила для мобильных устройств, у которых для параметра **енаблемобилити** задано значение true.</span><span class="sxs-lookup"><span data-stu-id="f1712-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="f1712-117">Чтобы пользователи могли использовать функцию "звонок с помощью работы", они должны удовлетворять следующим двум дополнительным требованиям:</span><span class="sxs-lookup"><span data-stu-id="f1712-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="f1712-118">Пользователям должна быть назначена политика голосовой связи, на которой установлен флажок **включить Одновременный звонок для телефонов** .</span><span class="sxs-lookup"><span data-stu-id="f1712-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="f1712-119">Пользователям должны быть назначены правила для мобильных устройств, у которых для параметра **енаблеаутсидевоице** задано значение true.</span><span class="sxs-lookup"><span data-stu-id="f1712-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1712-120">Пользователи, не поддерживающие корпоративную голосовую почту, могут использовать свои мобильные устройства, чтобы сделать Lync для голосовой связи Lync по протоколу IP (VoIP), или присоединиться к конференциям с помощью ссылки Click to Join на мобильных устройствах, если вы назначаете этим пользователям соответствующие параметры для политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f1712-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="f1712-121">Подробности можно найти <A href="lync-server-2013-defining-your-mobility-requirements.md">в разделе Определение требований к мобильным технологиям для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f1712-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f1712-122">Дополнительные сведения о включении пользователей для Lync Server 2013 можно найти в разделе [Отключение и повторное включение учетной записи пользователя в Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="f1712-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="f1712-123">Дополнительные сведения о включении поддержки пользователей для корпоративной голосовой связи можно найти [в разделе Включение поддержки пользователей для предприятий в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="f1712-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="f1712-124">Подробнее о настройке параметров политики голосовой связи можно узнать [в статьях изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="f1712-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="f1712-125">Изменение глобальной политики мобильности</span><span class="sxs-lookup"><span data-stu-id="f1712-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="f1712-126">Войдите в систему на любом компьютере, на котором установлена оболочка Lync Server Management Shell и Окскоре, как участник роли Ксадминистратор.</span><span class="sxs-lookup"><span data-stu-id="f1712-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f1712-127">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1712-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1712-128">Отключите доступ к мобильным технологиям и звоните с помощью глобальной работы.</span><span class="sxs-lookup"><span data-stu-id="f1712-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="f1712-129">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f1712-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f1712-130">Вы можете отключить функцию "звонок через", не отключив доступ к мобильному рабочему каналу.</span><span class="sxs-lookup"><span data-stu-id="f1712-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="f1712-131">Однако вы не можете отключить функцию мобильной связи, не отключив и не отключая Звонок через работу.</span><span class="sxs-lookup"><span data-stu-id="f1712-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="f1712-132">Изменение политики мобильной связи по сайту</span><span class="sxs-lookup"><span data-stu-id="f1712-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="f1712-133">Войдите в систему на любом компьютере, на котором установлена оболочка Lync Server Management Shell и Окскоре, как участник роли Ксадминистратор.</span><span class="sxs-lookup"><span data-stu-id="f1712-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f1712-134">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1712-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1712-135">Создание политики на уровне сайта и отключение VoIP и видео, включение функции "требовать WiFi для IP-звука" и для IP-видео по сайту.</span><span class="sxs-lookup"><span data-stu-id="f1712-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="f1712-136">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f1712-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="f1712-137">Изменение политики мобильности с помощью пользователя</span><span class="sxs-lookup"><span data-stu-id="f1712-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="f1712-138">Войдите в систему на любом компьютере, на котором установлена оболочка Lync Server Management Shell и Окскоре, как участник роли Ксадминистратор.</span><span class="sxs-lookup"><span data-stu-id="f1712-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f1712-139">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1712-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1712-140">Создавайте политики мобильности на уровне пользователей и отключайте мобильность и звоните по рабочему телефону.</span><span class="sxs-lookup"><span data-stu-id="f1712-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="f1712-141">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f1712-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="f1712-142">Вы можете отключить функцию "звонок через", не отключив доступ к мобильному рабочему каналу.</span><span class="sxs-lookup"><span data-stu-id="f1712-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="f1712-143">Однако вы не можете отключить функцию мобильной связи, не отключив и не отключая Звонок через работу.</span><span class="sxs-lookup"><span data-stu-id="f1712-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="f1712-144">Например:</span><span class="sxs-lookup"><span data-stu-id="f1712-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1712-145">См. также</span><span class="sxs-lookup"><span data-stu-id="f1712-145">See Also</span></span>


[<span data-ttu-id="f1712-146">Отключение и повторное включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1712-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="f1712-147">Включение пользователей корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1712-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="f1712-148">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1712-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="f1712-149">Определение требований к мобильной работе для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1712-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="f1712-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f1712-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="f1712-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f1712-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="f1712-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f1712-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="f1712-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f1712-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="f1712-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f1712-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

