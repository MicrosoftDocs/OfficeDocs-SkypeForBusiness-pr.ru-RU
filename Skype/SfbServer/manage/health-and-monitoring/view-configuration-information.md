---
title: Просмотр сведений о конфигурации CDR в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Сводка: сведения о том, как использовать запись сведений о звонке (CDR) в Skype для бизнеса Server.'
ms.openlocfilehash: 976f61ac98cb02a0cd69750a581bfa5190156ff7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991684"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="54077-103">Просмотр сведений о конфигурации CDR в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="54077-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="54077-104">**Сводка:** Сведения о том, как использовать запись сведений о звонке (CDR) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54077-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="54077-p101">Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.</span><span class="sxs-lookup"><span data-stu-id="54077-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="54077-107">При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="54077-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="54077-108">Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="54077-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="54077-109">Вы можете просматривать параметры конфигурации CDR, используемые в Организации, с помощью панели управления Skype для бизнеса Server или командлетом [Get-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="54077-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="54077-110">Просмотр сведений о конфигурации CDR с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="54077-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="54077-111">На панели управления Skype для бизнеса Server нажмите кнопку **наблюдение и архивация**.</span><span class="sxs-lookup"><span data-stu-id="54077-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="54077-p103">Список всех параметров конфигурации CDR отображается на вкладке **Регистрация вызовов**. Для каждой коллекции параметров вы увидите **Имя**, была ли включена регистрация вызовов или нет (свойство **CDR**) независимо от включения очистки (свойство **Очистка CDR**). Для просмотра подробных сведений о коллекции дважды щелкните ее или выберите нужную коллекцию, нажмите кнопку **Правка** и щелкните **Показать подробности**. Учтите, что вы можете просматривать подробную информацию только для одной коллекции параметров конфигурации CDR за один раз.</span><span class="sxs-lookup"><span data-stu-id="54077-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="54077-115">Просмотр сведений о конфигурации CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54077-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="54077-116">Вы можете просматривать параметры конфигурации CDR с помощью Windows PowerShell и командлета Get-Кскдрконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="54077-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="54077-117">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54077-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="54077-118">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="54077-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="54077-119">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54077-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="54077-120">Просмотр данных конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="54077-120">To view CDR configuration information</span></span>

- <span data-ttu-id="54077-121">Чтобы просмотреть сведения о всех параметрах конфигурации CDR, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="54077-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="54077-122">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="54077-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="54077-123">Дополнительные сведения можно найти в разделе справки по командлету [Get-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="54077-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

