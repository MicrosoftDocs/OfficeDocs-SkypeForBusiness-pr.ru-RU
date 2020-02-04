---
title: 'Lync Server 2013: изменение параметров качества взаимодействия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2cf4745f76fa4667d14c9da5ca2b4e5309767b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="75304-102">Изменение параметров качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75304-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75304-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="75304-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="75304-p101">По умолчанию данные о качестве взаимодействия удаляются каждые 60 дней. Чтобы изменить срок хранения данных, используйте параметры на странице **Данные о качестве взаимодействия**. При отключении записи данных о качестве взаимодействия все собранные ранее данные будут удалены.</span><span class="sxs-lookup"><span data-stu-id="75304-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75304-p102">Вам нужно задать одинаковый период хранения данных функции регистрации вызовов (CDR) и данных о качестве взаимодействия. Каждый звонок, отраженный в отчетах регистрации вызовов, доступен на домашней странице отчетов сервера мониторинга и содержит как данные функции регистрации вызовов, так и данные о качестве взаимодействия. Если сроки хранения данных функции регистрации вызовов и данных о качестве взаимодействия отличаются, то некоторые вызовы могут содержать только данные функции регистрации вызовов, а другие — только данные о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="75304-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="75304-110">Ниже даны инструкции по настройке параметров очистки данных о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="75304-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="75304-111">Определение хранения данных QoE с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="75304-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="75304-112">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="75304-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="75304-113">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="75304-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="75304-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75304-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75304-115">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75304-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75304-116">На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="75304-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="75304-117">На странице **Данные о качестве взаимодействия** выберите требуемый сайт в таблице, нажмите **Изменить** и выберите **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="75304-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="75304-118">Чтобы включить очистку, выберите **Разрешить очистку данных о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="75304-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="75304-119">В поле **Хранить данные о качестве взаимодействия не дольше (дн.)** выберите максимальный срок хранения данных о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="75304-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="75304-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="75304-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75304-121">Указание хранения QoE с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75304-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="75304-122">Вы можете создать параметры хранения QoE с помощью Windows PowerShell и командлета **Set-кскоеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="75304-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="75304-123">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75304-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="75304-124">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75304-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="75304-125">Указание срока хранения данных о качестве взаимодействия для определенного расположения</span><span class="sxs-lookup"><span data-stu-id="75304-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="75304-126">Эта команда включает очистку данных о качестве взаимодействия и настраивает их хранение в течение 20 дней для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="75304-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="75304-127">Указание срока хранения данных о качестве взаимодействия для нескольких расположений</span><span class="sxs-lookup"><span data-stu-id="75304-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="75304-128">Эта команда настраивает срок хранения для всех параметров конфигурации качества взаимодействия, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="75304-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="75304-129">Дополнительные сведения можно найти в разделе справки по командлету [Set-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="75304-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75304-130">См. также</span><span class="sxs-lookup"><span data-stu-id="75304-130">See Also</span></span>


[<span data-ttu-id="75304-131">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75304-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

