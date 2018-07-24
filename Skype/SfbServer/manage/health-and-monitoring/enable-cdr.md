---
title: Включение регистрации вызовов в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Сводка: Узнайте, как включить регистрации вызовов (CDR) записей в Скайп для Business Server.'
ms.openlocfilehash: 55fafd037e271166eaf94b460f656b811720e00f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995743"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="d98ef-103">Включение регистрации вызовов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d98ef-103">Enable call detail recording in Skype for Business Server</span></span>
 
<span data-ttu-id="d98ef-104">**Сводка:** Узнайте, как включить регистрации вызовов (CDR) записей в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="d98ef-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>
  
<span data-ttu-id="d98ef-p101">Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями.</span><span class="sxs-lookup"><span data-stu-id="d98ef-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> 
  
<span data-ttu-id="d98ef-107">Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.</span><span class="sxs-lookup"><span data-stu-id="d98ef-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d98ef-108">Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d98ef-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="d98ef-109">Дополнительные сведения см [Развертывание мониторинга](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="d98ef-109">For details, see [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span> 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="d98ef-110">Чтобы включить CDR с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="d98ef-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d98ef-111">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server .</span><span class="sxs-lookup"><span data-stu-id="d98ef-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="d98ef-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="d98ef-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d98ef-113">В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.</span><span class="sxs-lookup"><span data-stu-id="d98ef-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span> 
    
4. <span data-ttu-id="d98ef-114">На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.</span><span class="sxs-lookup"><span data-stu-id="d98ef-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d98ef-115">По умолчанию функция CDR включена.</span><span class="sxs-lookup"><span data-stu-id="d98ef-115">CDR is enabled by default.</span></span> 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d98ef-116">Включение CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d98ef-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d98ef-117">Можно включить CDR с помощью командлета **Set-CsCdrConfiguration** и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d98ef-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d98ef-118">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d98ef-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d98ef-119">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="d98ef-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d98ef-120">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="d98ef-120">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="d98ef-121">Включение CDR для отдельного места</span><span class="sxs-lookup"><span data-stu-id="d98ef-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="d98ef-122">Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="d98ef-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="d98ef-123">Чтобы отключить CDR для отдельного места</span><span class="sxs-lookup"><span data-stu-id="d98ef-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="d98ef-p104">Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False). Отключение CDR не приводит к удалению мониторинга. Оно приостанавливает сбор и сохранение данных CDR.</span><span class="sxs-lookup"><span data-stu-id="d98ef-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="d98ef-127">Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="d98ef-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="d98ef-128">Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.</span><span class="sxs-lookup"><span data-stu-id="d98ef-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

<span data-ttu-id="d98ef-129">Для получения дополнительных сведений см раздел справки для командлета [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d98ef-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d98ef-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d98ef-130">See also</span></span>

[<span data-ttu-id="d98ef-131">Планирование мониторинга</span><span class="sxs-lookup"><span data-stu-id="d98ef-131">Planning for Monitoring</span></span>](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[<span data-ttu-id="d98ef-132">Мониторинг развертывания</span><span class="sxs-lookup"><span data-stu-id="d98ef-132">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)