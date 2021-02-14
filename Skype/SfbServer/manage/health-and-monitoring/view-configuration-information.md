---
title: Просмотр сведений о конфигурации CDR в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: Сводка. Узнайте, как использовать регистрацию вызовов (CDR) в Skype для бизнеса Server.
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816639"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="4e263-103">Просмотр сведений о конфигурации CDR в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4e263-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="4e263-104">**Сводка:** Узнайте, как использовать регистрацию вызовов (CDR) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4e263-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="4e263-p101">Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.</span><span class="sxs-lookup"><span data-stu-id="4e263-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="4e263-107">При установке Skype для бизнеса Server создается одна глобальная коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="4e263-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="4e263-108">Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="4e263-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="4e263-109">Параметры конфигурации CDR, которые используются в организации, можно просмотреть с помощью панели управления Skype для бизнеса Server или с помощью [cmdlet Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4e263-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4e263-110">Просмотр сведений о конфигурации CDR с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4e263-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4e263-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span><span class="sxs-lookup"><span data-stu-id="4e263-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="4e263-p103">Список всех параметров конфигурации CDR отображается на вкладке **Регистрация вызовов**. Для каждой коллекции параметров вы увидите **Имя**, была ли включена регистрация вызовов или нет (свойство **CDR**) независимо от включения очистки (свойство **Очистка CDR**). Для просмотра подробных сведений о коллекции дважды щелкните ее или выберите нужную коллекцию, нажмите кнопку **Правка** и щелкните **Показать подробности**. Учтите, что вы можете просматривать подробную информацию только для одной коллекции параметров конфигурации CDR за один раз.</span><span class="sxs-lookup"><span data-stu-id="4e263-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4e263-115">Просмотр сведений о конфигурации CDR с помощью Windows PowerShell управления</span><span class="sxs-lookup"><span data-stu-id="4e263-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4e263-116">Параметры конфигурации CDR можно просмотреть с помощью Windows PowerShell и Get-CsCdrConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="4e263-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="4e263-117">Вы можете запустить этот Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e263-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4e263-118">Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="4e263-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4e263-119">В Skype для бизнеса Server этот процесс тот же.</span><span class="sxs-lookup"><span data-stu-id="4e263-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="4e263-120">Просмотр данных конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="4e263-120">To view CDR configuration information</span></span>

- <span data-ttu-id="4e263-121">Чтобы просмотреть сведения обо всех параметрах конфигурации CDR, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="4e263-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="4e263-122">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="4e263-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="4e263-123">Дополнительные сведения см. в разделе справки по [cmdlet Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4e263-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

