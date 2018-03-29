---
title: Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Сводка: Узнайте, как для удаления параметров конфигурации CDR в Скайп для Business Server 2015.'
ms.openlocfilehash: d7379817b808ac800694c01014469fe0d159d68f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="313de-103">Удаление существующей коллекции параметров конфигурации CDR в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="313de-103">Delete an existing collection of CDR configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="313de-104">**Сводка:** Узнайте, как для удаления параметров конфигурации CDR в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="313de-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="313de-p101">Служба регистрации вызовов (CDR) позволяет отслеживать использование таких услуг, как сеансы обмена одноранговыми мгновенными сообщениями, телефонные вызовы с передачей речи по IP-сетям (VoIP) и вызовы конференц-связи. Данные о таком использовании телефонии включают сведения о том, кто кому звонил, когда звонили и каким долгим был телефонный разговор.</span><span class="sxs-lookup"><span data-stu-id="313de-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="313de-107">Когда вы устанавливаете Скайп для Business Server 2015, single, глобальной коллекции параметров конфигурации CDR будет создан автоматически.</span><span class="sxs-lookup"><span data-stu-id="313de-107">When you install Skype for Business Server 2015, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="313de-108">Администраторы также могут создавать настраиваемые коллекции параметров, которые можно применять к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="313de-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="313de-109">Параметры, настроенные на уровне сайта, переопределяют глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="313de-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="313de-110">Если удалить параметры уровня сайта, управление CDR на этом сайте будет осуществляться в соответствии с глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="313de-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="313de-111">Обратите внимание на то, что можно также «удалить» глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="313de-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="313de-112">Однако фактическое удаление глобальных параметров при этом не выполняется.</span><span class="sxs-lookup"><span data-stu-id="313de-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="313de-113">Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="313de-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="313de-114">Например по умолчанию очистку включена в коллекции параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="313de-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="313de-115">Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку.</span><span class="sxs-lookup"><span data-stu-id="313de-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="313de-116">Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="313de-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="313de-117">В данном случае это означает, что очистка будет снова включена.</span><span class="sxs-lookup"><span data-stu-id="313de-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="313de-118">Параметры конфигурации CDR можно удалить с помощью Скайп для панели управления сервера Business или командлет [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="313de-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="313de-119">Удаление параметров конфигурации CDR с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="313de-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="313de-120">В Скайп для панели управления Business Server щелкните **мониторинг и Архивация**.</span><span class="sxs-lookup"><span data-stu-id="313de-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="313de-p104">На вкладке **Регистрация вызовов** выберите коллекцию (или коллекции) параметров CDR для удаления. Чтобы выбрать несколько коллекций, выберите первую из них, нажмите и удерживайте клавишу Ctrl и щелкните дополнительные коллекции.</span><span class="sxs-lookup"><span data-stu-id="313de-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="313de-123">Нажмите **Изменить**, затем кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="313de-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="313de-124">В Скайп для диалогового окна панели управления Business Server нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="313de-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="313de-125">Удаление параметров конфигурации CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="313de-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="313de-126">Можно удалить регистрации вызовов параметров конфигурации с помощью Windows PowerShell и командлет **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="313de-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="313de-127">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="313de-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="313de-128">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="313de-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="313de-129">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="313de-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="313de-130">Удаление определенной коллекции параметров конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="313de-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="313de-131">Эта команда удаляет параметры конфигурации CDR, которые относятся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="313de-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="313de-132">Удаление всех параметров конфигурации CDR, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="313de-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="313de-133">Эта команда удаляет все параметры конфигурации CDR, применяемые на уровне сайта:</span><span class="sxs-lookup"><span data-stu-id="313de-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="313de-134">Удаление всех параметров конфигурации CDR, которые отключают регистрацию вызовов</span><span class="sxs-lookup"><span data-stu-id="313de-134">To remove all the CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="313de-135">Эта команда удаляет все параметры конфигурации CDR, которые отключают регистрацию вызовов:</span><span class="sxs-lookup"><span data-stu-id="313de-135">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="313de-136">Для получения дополнительных сведений см раздел справки по командлет [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="313de-136">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="313de-137">См. также</span><span class="sxs-lookup"><span data-stu-id="313de-137">See also</span></span>

[<span data-ttu-id="313de-138">Вручную удалить базы данных качества взаимодействия в Скайп и регистрации вызовов для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="313de-138">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

