---
title: Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: Сводка. Узнайте, как удалить параметры конфигурации CDR в Skype для бизнеса Server.
ms.openlocfilehash: 3ac961df352f26891ece9c69b7d62b37c4c015d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095313"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8acd2-103">Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8acd2-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="8acd2-104">**Сводка:** Узнайте, как удалить параметры конфигурации CDR в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8acd2-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="8acd2-p101">Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.</span><span class="sxs-lookup"><span data-stu-id="8acd2-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="8acd2-107">При установке Skype для бизнеса Server создается единая глобальная коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="8acd2-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="8acd2-108">Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="8acd2-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="8acd2-109">Параметры, настроенные на уровне сайта, переопределяют глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="8acd2-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="8acd2-110">Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="8acd2-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="8acd2-111">Обратите внимание, что можно также "удалить" глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="8acd2-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="8acd2-112">Однако фактическое удаление глобальных параметров при этом не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8acd2-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="8acd2-113">Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8acd2-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="8acd2-114">Например, по умолчанию чистка включена в наборе параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="8acd2-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="8acd2-115">Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку.</span><span class="sxs-lookup"><span data-stu-id="8acd2-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="8acd2-116">Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8acd2-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="8acd2-117">В данном случае это означает, что очистка будет снова включена.</span><span class="sxs-lookup"><span data-stu-id="8acd2-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="8acd2-118">Параметры конфигурации CDR можно удалить с помощью панели управления Skype для бизнес-серверов или группы [remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8acd2-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="8acd2-119">Удаление параметров конфигурации CDR с панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="8acd2-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8acd2-120">В панели управления Skype для бизнес-серверов нажмите **кнопку Мониторинг и архива.**</span><span class="sxs-lookup"><span data-stu-id="8acd2-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="8acd2-p104">На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, щелкните первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.</span><span class="sxs-lookup"><span data-stu-id="8acd2-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="8acd2-123">Щелкните **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8acd2-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="8acd2-124">В диалоговом окне Панель управления Skype для бизнес-серверов нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="8acd2-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8acd2-125">Удаление параметров конфигурации CDR с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="8acd2-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8acd2-126">Параметры конфигурации записи детализации вызовов можно удалить с помощью Windows PowerShell и **cmdlet Remove-CsCdrConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="8acd2-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="8acd2-127">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8acd2-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8acd2-128">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="8acd2-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="8acd2-129">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="8acd2-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="8acd2-130">Удаление определенной коллекции параметров конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="8acd2-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="8acd2-131">Эта команда удаляет параметры конфигурации CDR, которые относятся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="8acd2-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="8acd2-132">Удаление всех параметров конфигурации CDR, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="8acd2-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="8acd2-133">Эта команда удаляет все параметры конфигурации CDR, применяемые на уровне сайта:</span><span class="sxs-lookup"><span data-stu-id="8acd2-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="8acd2-134">Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8acd2-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8acd2-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8acd2-135">See also</span></span>

[<span data-ttu-id="8acd2-136">Вручную очищать записи детализации вызовов и базы данных по качеству работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8acd2-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)