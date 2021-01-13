---
title: Удаление параметров конфигурации качества работы в Skype для бизнеса Server
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: Сводка. Узнайте, как удалить параметры качества обслуживания (QoE) в Skype для бизнеса Server.
ms.openlocfilehash: 45150b6aa2e6f48eedb28f180cfff8f291f58abc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816939"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c3802-103">Удаление параметров конфигурации качества работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c3802-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c3802-104">**Сводка:** Узнайте, как удалить параметры качества обслуживания в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c3802-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c3802-p101">Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.</span><span class="sxs-lookup"><span data-stu-id="c3802-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="c3802-107">При установке Skype для бизнеса Server создается одна глобальная коллекция параметров конфигурации QoE.</span><span class="sxs-lookup"><span data-stu-id="c3802-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="c3802-108">Администраторы могут создавать пользовательские коллекции параметров, которые могут применяться к отдельным сайтам.</span><span class="sxs-lookup"><span data-stu-id="c3802-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="c3802-109">Параметры, настроенные на уровне сайта имеют более высокий приоритет, чем параметры, настроенные в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="c3802-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="c3802-110">В случае удаления параметров уровня сайта качество взаимодействия на этом сайте будет управляться с использованием глобальных параметров.</span><span class="sxs-lookup"><span data-stu-id="c3802-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="c3802-111">Обратите внимание, что вы также можете "удалить" глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="c3802-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="c3802-112">Однако фактическое удаление глобальных параметров при этом не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c3802-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="c3802-113">Вместо этого все свойства в этой коллекции сбрасываются на значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c3802-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="c3802-114">Например, по умолчанию в коллекции параметров конфигурации качества взаимодействия включена очистка.</span><span class="sxs-lookup"><span data-stu-id="c3802-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="c3802-115">Предположим, что вы изменяете глобальную коллекцию, чтобы отключить очистку.</span><span class="sxs-lookup"><span data-stu-id="c3802-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="c3802-116">Если вы позднее удаляете глобальные параметры, все свойства будут сброшены в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c3802-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="c3802-117">В данном случае это означает, что очистка будет снова включена.</span><span class="sxs-lookup"><span data-stu-id="c3802-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="c3802-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3802-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c3802-119">Удаление параметров конфигурации качества работы с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c3802-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c3802-120">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c3802-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c3802-121">Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="c3802-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c3802-122">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c3802-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c3802-123">В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="c3802-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="c3802-124">На странице **Данные о качестве взаимодействия** щелкните требуемую политику, щелкните элементы **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c3802-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="c3802-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c3802-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c3802-126">Удаление параметров конфигурации QoE с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3802-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c3802-127">Параметры конфигурации QoE можно удалить с помощью Windows PowerShell и с помощью Windows PowerShell **Remove-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="c3802-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="c3802-128">Вы можете запустить этот Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3802-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c3802-129">Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с помощью удаленной службы PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="c3802-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c3802-130">В Skype для бизнеса Server этот процесс тот же.</span><span class="sxs-lookup"><span data-stu-id="c3802-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="c3802-131">Удаление указанной коллекции параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="c3802-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="c3802-132">Эта команда удаляет параметры конфигурации качества взаимодействия, примененные к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="c3802-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="c3802-133">Удаление всех параметров конфигурации качества взаимодействия, примененных на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="c3802-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="c3802-134">Эта команда удаляет все параметры конфигурации качества взаимодействия, примененные на уровне сайта:</span><span class="sxs-lookup"><span data-stu-id="c3802-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="c3802-135">Удаление всех параметров конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия</span><span class="sxs-lookup"><span data-stu-id="c3802-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="c3802-136">Эта команда удаляет все параметры конфигурации качества взаимодействия с отключенным наблюдением за качеством взаимодействия:</span><span class="sxs-lookup"><span data-stu-id="c3802-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="c3802-137">Подробные сведения см. в [подстроке Remove-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c3802-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c3802-138">См. также</span><span class="sxs-lookup"><span data-stu-id="c3802-138">See also</span></span>

[<span data-ttu-id="c3802-139">Ручная очистка баз данных регистрации вызовов и качества обслуживания в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c3802-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

