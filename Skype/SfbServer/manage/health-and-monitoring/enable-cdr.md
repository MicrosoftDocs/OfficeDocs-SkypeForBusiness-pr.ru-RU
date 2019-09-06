---
title: Включение записи сведений о звонках в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Сводка: сведения о том, как включить запись сведений о звонке (CDR) в Skype для бизнеса Server.'
ms.openlocfilehash: 015ac3b57420401894e82c267e9737990ca7affb
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767061"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="ffaf4-103">Включение записи сведений о звонках в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ffaf4-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="ffaf4-104">**Сводка:** Сведения о том, как включить запись сведений о звонке (CDR) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="ffaf4-p101">Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="ffaf4-107">Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="ffaf4-p102">Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга. Дополнительные сведения см. в разделе [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="ffaf4-p102">In order to enable CDR you must configure monitoring and a monitoring database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="ffaf4-110">Включение CDR с помощью панели управления "Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="ffaf4-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ffaf4-111">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="ffaf4-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="ffaf4-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ffaf4-113">В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="ffaf4-114">На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ffaf4-115">По умолчанию функция CDR включена.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ffaf4-116">Включение CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffaf4-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ffaf4-117">Вы можете включить CDR с помощью Windows PowerShell и командлета **Set-кскдрконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="ffaf4-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="ffaf4-118">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ffaf4-119">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="ffaf4-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ffaf4-120">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="ffaf4-121">Включение CDR для отдельного места</span><span class="sxs-lookup"><span data-stu-id="ffaf4-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="ffaf4-122">Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="ffaf4-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="ffaf4-123">Чтобы отключить CDR для отдельного места</span><span class="sxs-lookup"><span data-stu-id="ffaf4-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="ffaf4-p104">Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False). Отключение CDR не приводит к удалению мониторинга. Оно приостанавливает сбор и сохранение данных CDR.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="ffaf4-127">Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="ffaf4-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="ffaf4-128">Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.</span><span class="sxs-lookup"><span data-stu-id="ffaf4-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="ffaf4-129">Дополнительные сведения можно найти в разделе справки по командлету [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ffaf4-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffaf4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ffaf4-130">See also</span></span>

[<span data-ttu-id="ffaf4-131">Планирование мониторинга</span><span class="sxs-lookup"><span data-stu-id="ffaf4-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="ffaf4-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="ffaf4-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
